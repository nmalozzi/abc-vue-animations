<template>
  <div class="group-flex">
    <div class="group-head">
      <h2 v-if="header">{{ header }}</h2>
      <p v-if="smallText">{{ smallText }}</p>
    </div>
    <div class="input-group">
      <div class="input-wrap" v-for="(option, index) in options" :key="option">
        <input
            type="radio"
            :id="option"
            @change="$emit('input', $event.target.value)"
            :name="group"
            :value="option"
            :checked="index === defaultSelected"
        />
        <label :for="option">
          {{ option }}
          <svg class="radio-button" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 131.75 131.75"><circle cx="65.87" cy="65.87" r="65.87" fill="#41aa54"/><path d="M67.24 126.36c-6.33 0-12.63-1.01-18.86-3.04a2.398 2.398 0 0 1-1.54-3.03 2.406 2.406 0 0 1 3.03-1.54c12.66 4.12 25.65 3.69 38.62-1.29 1.25-.48 2.63.15 3.11 1.39s-.14 2.63-1.38 3.11c-7.67 2.93-15.35 4.4-22.98 4.4zM29.89 113.35c-.43 0-.87-.12-1.26-.36-6.16-3.8-9.44-9.17-9.58-9.39-.69-1.14-.32-2.62.82-3.3 1.13-.68 2.61-.32 3.3.81.04.06 2.86 4.63 7.99 7.79a2.403 2.403 0 0 1-1.27 4.45z" fill="#fff"/><path d="M65.96 114.28c-14.15 0-25.76-6.07-31.69-11.22a7.221 7.221 0 0 1-.71-10.19c2.61-3 7.15-3.33 10.16-.74.88.75 20.92 17.26 45.54-.39 3.24-2.32 7.75-1.58 10.07 1.66 2.32 3.24 1.58 7.75-1.66 10.07-11.1 7.95-22 10.81-31.71 10.81z" fill="#018837" opacity=".5"/><circle cx="38.34" cy="116.55" r="4.05" fill="#fff"/><path d="M36.03 43.46c-2.4 0-4.77-1.12-6.28-3.22-2.48-3.46-1.69-8.29 1.78-10.77 29.15-20.9 57.08-8.85 67.78.45 3.22 2.8 3.56 7.67.76 10.89a7.716 7.716 0 0 1-10.86.79c-.94-.8-22.36-18.45-48.69.42a7.709 7.709 0 0 1-4.49 1.44z" fill="#018837" opacity=".5"/><path d="M105.06 26.53c-.73 0-1.45-.31-1.96-.9-.04-.04-3.8-4.39-9.76-6.86a2.567 2.567 0 0 1-1.39-3.36 2.567 2.567 0 0 1 3.36-1.39c7.15 2.96 11.53 8.07 11.71 8.28a2.58 2.58 0 0 1-.3 3.63c-.48.4-1.07.6-1.66.6z" fill="#fff"/></svg>
        </label>
      </div>
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
    smallText: {
      default: undefined,
      type: String
    },
    group: {
      required: true,
      type: String,
    },
    defaultSelected: {
      type: Number,
      default: 0
    },
  },
};
</script>

<style scoped>
.group-flex {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-direction: row;
}

.input-group {
  display: flex;
  flex-wrap: wrap;
  width: auto;
}

.input-wrap {
  width: 56px;
  text-align: center;
  margin: 0 8px;
}

label {
  cursor: pointer;
  color: #333;
}

.radio-button {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  box-shadow: 0 12px 0 -4px #cccccc;
  margin-top: 8px;
}

input[type="radio"] {
  position: fixed;
  opacity: 0;
  pointer-events: none;
}

input[type="radio"]:checked+label .radio-button {
  box-shadow: 0 0 4px 4px #45D657;
  width: 48px;
  height: 48px;
  transform: translateY(4px);
}

.group-head p { margin: 8px 0 0 0; }


@media only screen and (max-width: 600px) {
  .group-head { text-align: center; }
  .group-flex { flex-direction: column; }
  .input-wrap { margin: 16px 4px 0 4px}
}
</style>