<template>
  <div>
    <label :for="id + '-button'" :class="{'active': isActive}" class="toggle-button">
      <h2 class="toggle-label">{{ labelDisableText }}</h2>
      <input type="checkbox" :id="id + '-button'" v-model="checkedValue">
      <span class="toggle-switch"></span>
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
  height: 12px;
  border-radius: 6px;
  width: 40px;
  background: #BFCBD9;
  box-shadow: inset 0 0 1px #BFCBD9;
  position: relative;
  margin: 0 10px;
  transition: all .25s;
}

.toggle-button .toggle-switch::after,
.toggle-button .toggle-switch::before {
  content: "";
  position: absolute;
  display: block;
  height: 18px;
  width: 18px;
  border-radius: 50%;
  left: 0;
  top: -3px;
  transform: translateX(0);
  transition: all .25s cubic-bezier(.5, -.6, .5, 1.6);
}

.toggle-button .toggle-switch::after {
  background: #4D4D4D;
  box-shadow: 0 0 1px #666;
}

.toggle-button .toggle-switch::before {
  background: #4D4D4D;
  box-shadow: 0 0 0 3px rgba(0, 0, 0, 0.1);
  opacity: 0;
}

.active .toggle-switch {
  background: #adedcb;
  box-shadow: inset 0 0 1px #adedcb;
}

.active .toggle-switch::after,
.active .toggle-switch::before {
  transform: translateX(40px -18px);
}

.active .toggle-switch::after {
  left: 23px;
  background: #53B883;
  box-shadow: 0 0 1px #53B883;
}
</style>