<template>
  <div class="input-group">
    <h2 v-if="header">{{ header }}</h2>
    <div v-for="(option, index) in options" :key="option">
      <label :for="option">
        <input
            type="radio"
            :id="option"
            @change="$emit('input', $event.target.value)"
            :name="group"
            :value="option"
            :checked="index === 0"
        />
        {{ option }}
      </label>
    </div>
  </div>
</template>

<script>

export default {
  props: {
    options: {
      required: true,
      type: Array,
    },
    header: {
      default: undefined,
      type: String
    },
    group: {
      required: true,
      type: String,
    },
  },
};
</script>

<style scoped>
.input-group {
  width: 35%;
  margin: 20px 0;
  padding: 15px 20px;
  display: flex;
  justify-content: space-between;
}

label {
  cursor: pointer;
}
</style>