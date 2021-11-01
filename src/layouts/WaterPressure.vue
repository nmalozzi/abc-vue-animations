<template>
  <div>
    <h1>{{ header }}</h1>
    <OutputNumeric label="gallons per minute" />
    <ToggleButton id="switch" />
    <SliderBar />
    <PlusMinusInput />
  </div>
</template>

<script>
import ToggleButton from '@/components/ToggleButton.vue'
import SliderBar from '@/components/SliderBar.vue'
import PlusMinusInput from "@/components/PlusMinusInput";
import OutputNumeric from "@/components/OutputNumeric";

export default {
  props: {
    header: String
  },
  components: {
    OutputNumeric,
    PlusMinusInput,
    ToggleButton,
    SliderBar
  }
}
</script>
