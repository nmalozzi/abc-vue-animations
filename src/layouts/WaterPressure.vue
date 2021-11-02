<template>
  <div>
    <h1>{{ header }}</h1>
    <OutputNumeric :output="output" label="gallons per minute" />



<!--    <ToggleButton id="switch" />-->
    <!--Length of Tubing-->
    <PlusMinusInput v-model.number="tubeLength" label="Length of Tubing" :step=minTubeLength :min=minTubeLength :max=maxTubeLength />
    <PlusMinusInput v-model.number="secondNumber" />

  </div>
</template>

<script>
// import ToggleButton from '@/components/ToggleButton.vue'
import PlusMinusInput from "@/components/PlusMinusInput";
import OutputNumeric from "@/components/OutputNumeric";

export default {
  data() {
    return {
      secondNumber: 2,
      tubeLength: 25,
      tubeLengthFlowRates: {
        25: 1,
        50: .58,
        75: .54,
        100: .5
      }
    }
  },
  computed: {
    minTubeLength: function(){
      return parseInt(Object.keys(this.tubeLengthFlowRates)[0]);
    },
    maxTubeLength: function(){
      return parseInt(Object.keys(this.tubeLengthFlowRates)[Object.keys(this.tubeLengthFlowRates).length - 1]);
    },
    output: function(){
      return this.tubeLengthFlowRates[this.tubeLength] * this.secondNumber;
    }
  },
  props: {
    header: String
  },
  components: {
    OutputNumeric,
    PlusMinusInput,
    // ToggleButton,
  }
}

</script>
