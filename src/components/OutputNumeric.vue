<template>
  <div class="output-numeric">
    <svg class="glare" x="0" y="0" viewBox="0 0 20.12 24.9"><path style="fill:#ffffff" d="M5.92 16.34c-.3 0-.6-.05-.9-.17a2.496 2.496 0 0 1-1.43-3.23c2.48-6.4 6.8-10.59 13.22-12.8 1.31-.45 2.73.24 3.18 1.55.45 1.31-.24 2.73-1.55 3.18-5.01 1.73-8.25 4.86-10.19 9.87a2.5 2.5 0 0 1-2.33 1.6z"/><circle style="fill:#ffffff" cx="2.96" cy="21.94" r="2.96"/></svg>
    <div class="output-value">
      {{ output }}
    </div>
    <div class="output-label">
      {{ label }}
    </div>
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

<style scoped>
.output-numeric {
  position: relative;
  border: 12px solid #01A0C6;
  border-radius: 16px;
  background: #E5E5E5;
  padding: 24px;
  display: flex;
  align-items: flex-end;
}

.output-numeric svg.glare {
  position: absolute;
  top: -8px;
  left: -8px;
  width: 12px;
}

.output-numeric .output-value {
  border: 1px solid #000;
  padding: 8px 24px;
  font-size: 100px;
  font-family: ds-digi, sans-serif;
  width: 220px;
  text-align: right;
}

.output-numeric .output-label {
  padding: 16px;
  font-size: 40px;
  font-family: ds-digi, sans-serif;
  font-weight: bold;
  text-transform: capitalize;
}
</style>