<template>
  <div>
    <p>{{ output }} {{ label }}</p>
  </div>
</template>

<script>
export default {
  props: {
    output: Number,
    label: String
  }
}
</script>
