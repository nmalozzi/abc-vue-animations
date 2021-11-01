<template>
  <div>
    <h1>{{ header }}</h1>
    <ToggleButton id="switch" />
  </div>
</template>

<script>
import ToggleButton from '../components/ToggleButton.vue'

export default {
  name: 'WaterPressureLayout',
  props: {
    header: String
  },
  components: {
    ToggleButton
  }
}
</script>
