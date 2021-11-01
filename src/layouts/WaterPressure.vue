<template>
  <div>
    <h1>{{ header }}</h1>
    <ToggleButton id="switch" />
    <SliderBar />
  </div>
</template>

<script>
import ToggleButton from '../components/ToggleButton.vue'
import SliderBar from '../components/SliderBar.vue'

export default {
  name: 'WaterPressureLayout',
  props: {
    header: String
  },
  components: {
    ToggleButton,
    SliderBar
  }
}
</script>
