<template>
  <div>
    <label :for="id + '-button'" :class="{'active': isActive}" class="toggle-button">
      <h2 class="toggle-label">{{ labelDisableText }}</h2>
      <input type="checkbox" :id="id + '-button'" v-model="checkedValue">
      <span class="toggle-switch">
        <svg class="off" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 172 137" xml:space="preserve"><path d="M29.35 135.98C13.72 135.98 1 123.26 1 107.63s12.72-28.35 28.35-28.35S57.7 92 57.7 107.63s-12.72 28.35-28.35 28.35zm0-43.94c-8.6 0-15.59 6.99-15.59 15.59s6.99 15.59 15.59 15.59 15.59-7 15.59-15.59-6.99-15.59-15.59-15.59z" fill="#b3b3b3"/><circle cx="29.35" cy="106.56" r="24.17" fill="gray" stroke="#ccc" stroke-width="3" stroke-miterlimit="10"/><path d="m28.3 88.97 70.86-73.56c20.06-22.29 48.09-16.92 62.9 3.82.41.58.81 1.17 1.2 1.77 3.53 5.52 5.6 11.56 6.3 17.66 2.13 18.67-9.46 36.21-27.07 42.76l-99.15 36.91c-16.62 7.76-34.52-13.71-15.04-29.36z" fill="#ccc"/><path d="m44.95 95.49 51.34-53.47c5.6-7.01 27.9-21.42 44.1-1.12 9.28 11.63 6.2 29.91-15.03 39.66l-73.9 26c-4.42-1.19-8.36-6.8-6.51-11.07z" fill="#bfbfbf"/><path d="M158.16 56.52c-.41 0-.83-.08-1.24-.24a3.39 3.39 0 0 1-1.91-4.4c.33-.85 7.93-21.23-11.46-33.81a3.391 3.391 0 0 1 3.69-5.69c24.1 15.64 14.18 41.72 14.08 41.98a3.406 3.406 0 0 1-3.16 2.16z" fill="#fff"/><circle cx="129.67" cy="27.09" r="8.08" fill="#fff"/><path fill="#f2f2f2" d="m59.48 63.51-15 15.44"/><path d="M44.48 80.65a1.702 1.702 0 0 1-1.22-2.88l15-15.45c.65-.67 1.72-.69 2.4-.03.67.65.69 1.72.04 2.4l-15 15.45c-.33.34-.78.51-1.22.51z" fill="#fff"/><g><path d="M115.64 13.48c-.46 0-.91-.18-1.24-.54a1.7 1.7 0 0 1 .09-2.39c.33-.3 8.11-7.37 20.37-3.46a1.695 1.695 0 1 1-1.03 3.23c-10.31-3.29-16.77 2.47-17.04 2.71-.33.31-.74.45-1.15.45z" fill="#fff"/></g></svg>
        <svg class="on" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 172 137" xml:space="preserve"><path d="M29.35 135.98C13.72 135.98 1 123.26 1 107.63s12.72-28.35 28.35-28.35S57.7 92 57.7 107.63s-12.72 28.35-28.35 28.35zm0-43.94c-8.6 0-15.59 6.99-15.59 15.59s6.99 15.59 15.59 15.59 15.59-7 15.59-15.59-6.99-15.59-15.59-15.59z" fill="#b3b3b3"/><circle cx="29.35" cy="106.56" r="24.17" fill="gray" stroke="#ccc" stroke-width="3" stroke-miterlimit="10"/><path d="m28.3 88.97 70.86-73.56c20.06-22.29 48.09-16.92 62.9 3.82.41.58.81 1.17 1.2 1.77 3.53 5.52 5.6 11.56 6.3 17.66 2.13 18.67-9.46 36.21-27.07 42.76l-99.15 36.91c-16.62 7.76-34.52-13.71-15.04-29.36z" fill="#ccc"/><path d="m44.95 95.49 51.34-53.47c5.6-7.01 27.9-21.42 44.1-1.12 9.28 11.63 6.2 29.91-15.03 39.66l-73.9 26c-4.42-1.19-8.36-6.8-6.51-11.07z" fill="#bfbfbf"/><path d="M158.16 56.52c-.41 0-.83-.08-1.24-.24a3.39 3.39 0 0 1-1.91-4.4c.33-.85 7.93-21.23-11.46-33.81a3.391 3.391 0 0 1 3.69-5.69c24.1 15.64 14.18 41.72 14.08 41.98a3.406 3.406 0 0 1-3.16 2.16z" fill="#fff"/><circle cx="129.67" cy="27.09" r="8.08" fill="#fff"/><path fill="#f2f2f2" d="m59.48 63.51-15 15.44"/><path d="M44.48 80.65a1.702 1.702 0 0 1-1.22-2.88l15-15.45c.65-.67 1.72-.69 2.4-.03.67.65.69 1.72.04 2.4l-15 15.45c-.33.34-.78.51-1.22.51z" fill="#fff"/><g><path d="M115.64 13.48c-.46 0-.91-.18-1.24-.54a1.7 1.7 0 0 1 .09-2.39c.33-.3 8.11-7.37 20.37-3.46a1.695 1.695 0 1 1-1.03 3.23c-10.31-3.29-16.77 2.47-17.04 2.71-.33.31-.74.45-1.15.45z" fill="#fff"/></g></svg>
      </span>
      <h2 class="toggle-label">{{ labelEnableText }}</h2>
    </label>
  </div>
</template>

<script>
export default {
  props: {
    labelEnableText: {
      type: String,
      default: 'On'
    },
    labelDisableText: {
      type: String,
      default: 'Off'
    },
    id: {
      type: String,
      default: 'primary'
    },
    defaultState: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      currentState: this.defaultState
    }
  },
  watch: {
    defaultState: function defaultState() {
      this.currentState = Boolean(this.defaultState)
    }
  },
  computed: {
    isActive() {
      return this.currentState;
    },
    checkedValue: {
      get() {
        return this.currentState;
      },
      set(newValue) {
        this.currentState = newValue;
        this.$emit('change', newValue);
      }
    }
  }
}
</script>

<style scoped>
.toggle-button {
  vertical-align: middle;
  user-select: none;
  cursor: pointer;
}

.toggle-button h2 {
  display: inline-block;
}

.toggle-button input[type="checkbox"] {
  opacity: 0;
  position: absolute;
  width: 1px;
  height: 1px;
}

.toggle-button .toggle-switch {
  display: inline-block;
  width: 100px;
  position: relative;
  margin: 0;
  text-align: center;
}

.toggle-button .toggle-switch svg.off {
  width: 50px;
  margin-right: -8px;
  transform: scaleX(-1);
  visibility: visible;
}

.toggle-button .toggle-switch svg.on {
  width: 50px;
  margin-left: -8px;
  visibility: hidden;
}

.toggle-button.active .toggle-switch svg.off {
  visibility: hidden;
}

.toggle-button.active .toggle-switch svg.on {
  visibility: visible;
}

</style>