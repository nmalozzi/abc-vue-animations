<template>
  <div>
    <h1>{{ header }}</h1>
    <ToggleButton id="switch" />
    <SliderBar />
    <PlusMinusInput />
  </div>
</template>

<script>
import ToggleButton from '@/components/ToggleButton.vue'
import SliderBar from '@/components/SliderBar.vue'
import PlusMinusInput from "@/components/PlusMinusInput";

export default {
  name: 'WaterPressureLayout',
  props: {
    header: String
  },
  components: {
    PlusMinusInput,
    ToggleButton,
    SliderBar
  }
}
</script>
