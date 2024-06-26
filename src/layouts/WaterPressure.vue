<template>
  <div class="water-pressure-animation">
    <OutputNumeric
        :output="+(output.toFixed(2))"
        label="gallons per minute"
        label-fine-print="Min 3/4 gallons per minute for WaterFed® Cleaning"
    />
    <div class="water-pressure-flex">
      <div class="water-pressure-meter">
        <OutputMeter
            :output="+(output.toFixed(2))"
            :meter-max=10
            :meter-min=0
        />
      </div>
      <div class="water-pressure-controls">
        <!--System Type-->
        <ToggleButton
            id="systemType"
            labelDisableText="Multistage"
            labelEnableText="Di Only"
            v-on:change="setSystemMultiplier"
        />
        <hr/>
        <!--Temperature-->
        <SliderBar
            :header="'Temperature: ' + temperature + 'F'"
            smallText="Temperature only has an effect if Multi-Stage is selected above. Temperature has no effect if DI Only is selected."
            v-model="temperature"
            :min="0"
            :max="99"
            :ticks="18"
        />
        <hr/>
        <!--Tap Pressure-->
        <RadioButtonGroup
            :options="Object.keys(this.tapPressureFlowRates)"
            v-model="tapPressure"
            header="Tap Pressure"
            group="tapPressure"
            :default-selected=1
        />
        <hr/>
        <!--Length of Hose-->
        <PlusMinusInput
            v-model.number="tubeLength"
            header="Length of Hose"
            smallText="Hose from system to pole."
            inputLabel="ft"
            :step=minTubeLength
            :min=minTubeLength
            :max=maxTubeLength
        />
        <hr/>
        <!--Hose Diameter-->
        <RadioButtonGroup
            :options="Object.keys(this.hoseDiameterFlowRates)"
            v-model="hoseDiameter"
            header="Hose Diameter"
            smallText="Hose from system to pole."
            group="hoseDiameter"
            :default-selected=2
        />
        <hr/>
        <!--Pump-->
        <ToggleButton
            id="pump"
            labelDisableText="Pump Off"
            labelEnableText="Pump On"
            v-on:change="setPumpMultiplier"
        />
        <hr/>
        <!--Flush Type-->
        <ToggleButton
            id="flushType"
            labelDisableText="Regular RO Flush"
            labelEnableText="No RO Flush"
            v-on:change="setFlushMultiplier"
        />
      </div>
    </div>
  </div>
</template>

<script>
import ToggleButton from '@/components/ToggleButton.vue'
import PlusMinusInput from "@/components/PlusMinusInput";
import OutputNumeric from "@/components/OutputNumeric";
import OutputMeter from "@/components/OutputMeter";
import RadioButtonGroup from "@/components/RadioButtonGroup";
import SliderBar from "@/components/SliderBar";

export default {
  components: {
    OutputNumeric,
    OutputMeter,
    PlusMinusInput,
    ToggleButton,
    RadioButtonGroup,
    SliderBar
  },
  data() {
    return {
      tubeLength: 25,
      tubeLengthFlowRates: {
        25: 1,
        50: .58,
        75: .54,
        100: .5
      },
      hoseDiameter: "3/8",
      hoseDiameterFlowRates: {
        "5/16": .15,
        "1/4": .25,
        "3/8": .9,
        "1/2": 1,
      },
      tapPressure: "60psi",
      tapPressureFlowRates: {
        "50psi": .75,
        "60psi": 1,
        "70psi": 1.25,
      },
      temperature: 77,
      systemMultiplier: 1,
      flushMultiplier: 1,
      pumpMultiplier: 1,
    }
  },
  methods: {
    setSystemMultiplier(value) {
      this.systemMultiplier = value ? 3 : 1;
    },
    setFlushMultiplier(value) {
      this.flushMultiplier = value && this.systemMultiplier === 1 ? .5 : 1;
    },
    setPumpMultiplier(value) {
      this.pumpMultiplier = value ? 2.5 : 1;
    },
  },
  computed: {
    minTubeLength: function () {
      return parseInt(Object.keys(this.tubeLengthFlowRates)[0]);
    },
    maxTubeLength: function () {
      return parseInt(Object.keys(this.tubeLengthFlowRates)[Object.keys(this.tubeLengthFlowRates).length - 1]);
    },
    temperatureMultiplier: function () {
      let multiplier = 1;

      if (this.systemMultiplier === 1) {
        if (this.temperature < 61) {
          multiplier = .75;
        }
        if (this.temperature < 46) {
          multiplier = .62;
        }
        if (this.temperature < 33) {
          multiplier = 0;
        }
      }

      return multiplier;
    },
    output: function () {
      return this.tubeLengthFlowRates[this.tubeLength]
          * this.systemMultiplier
          * this.flushMultiplier
          * this.pumpMultiplier
          * this.hoseDiameterFlowRates[this.hoseDiameter]
          * this.tapPressureFlowRates[this.tapPressure]
          * this.temperatureMultiplier;
    }
  },
}
</script>

<style scoped>

.water-pressure-animation {
  border-radius: 16px;
  background: #f5f5f5;
  padding: 16px;
  max-width: 800px;
  border: 4px inset #efeeee;
  margin: 0 auto 16px auto;
}

.water-pressure-flex {
  display: flex;
}

.water-pressure-meter {
  width: 100px;
  margin: 16px 16px 0 0;
  flex-shrink: 0;
}

.water-pressure-controls {
  flex-grow: 1;
  padding: 24px 0 16px 0;
}

hr {
  border: 1px dotted #ccc;
  margin: 24px 0;
}

@media only screen and (max-width: 375px) {
  .water-pressure-meter {
    display: none;
  }
}

</style>