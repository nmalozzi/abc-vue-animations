<template>
  <div>
    <h1>{{ output }} {{ label }}</h1>
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
