<template>
  <div>
    <OutputNumeric :output="+(output.toFixed(2))" label="gallons per minute"/>

    <!--System Type-->
    <ToggleButton
        id="systemType"
        labelDisableText="Multistage"
        labelEnableText="Di Only"
        v-on:change="setSystemMultiplier"
    />
    <hr/>
    <!--Length of Tubing-->
    <PlusMinusInput
        v-model.number="tubeLength"
        header="Length of Tubing"
        inputLabel="ft"
        :step=minTubeLength
        :min=minTubeLength
        :max=maxTubeLength
    />
    <hr/>
    <!--Flush Type-->
    <ToggleButton
        id="flushType"
        labelDisableText="Regular RO Flush"
        labelEnableText="No RO Flush"
        v-on:change="setFlushMultiplier"
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
    <!--Hose Diameter-->
    <RadioButtonGroup
        :options="Object.keys(this.hoseDiameterFlowRates)"
        v-model="hoseDiameter"
        header="Hose Diameter"
        group="hoseDiameter"
    />
    <hr/>
    <!--Hose Diameter-->
    <RadioButtonGroup
        :options="Object.keys(this.tapPressureFlowRates)"
        v-model="tapPressure"
        header="Tap Pressure"
        group="tapPressure"
    />
    <hr/>
    <!--Hose Diameter-->
    <span>Temperature: {{temperature}} </span>

    <SliderBar
        v-model="temperature"
        :min="0"
        :max="99"
        class="slider" />
  </div>


</template>

<script>
import ToggleButton from '@/components/ToggleButton.vue'
import PlusMinusInput from "@/components/PlusMinusInput";
import OutputNumeric from "@/components/OutputNumeric";
import RadioButtonGroup from "@/components/RadioButtonGroup";
import SliderBar from "@/components/SliderBar";

export default {
  components: {
    OutputNumeric,
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
      hoseDiameter: "5/16",
      hoseDiameterFlowRates: {
        "5/16": .15,
        "1/4": .25,
        "3/8": .9,
        "1/2": 1,
      },
      tapPressure: "50psi",
      tapPressureFlowRates: {
        "50psi": .75,
        "60psi": .1,
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
      this.flushMultiplier = value ? .5 : 1;
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

      if (this.systemMultiplier === 1 ) {
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