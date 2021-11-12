<template>
  <div class="plus-minus-input">
    <h2 v-if="header">{{ header }}</h2>
    <div>
      <div class="plus-minus-button minus" v-on:click="mpminus()">
        -
      </div>
      <div id="field">
        <svg class="glare" x="0" y="0" viewBox="0 0 20.12 24.9"><path style="fill:#ffffff" d="M5.92 16.34c-.3 0-.6-.05-.9-.17a2.496 2.496 0 0 1-1.43-3.23c2.48-6.4 6.8-10.59 13.22-12.8 1.31-.45 2.73.24 3.18 1.55.45 1.31-.24 2.73-1.55 3.18-5.01 1.73-8.25 4.86-10.19 9.87a2.5 2.5 0 0 1-2.33 1.6z"/><circle style="fill:#ffffff" cx="2.96" cy="21.94" r="2.96"/></svg>
        <input type="number" v-model="newValue" :step="step" disabled/>
        <span class="input-label">{{ inputLabel }}</span>
      </div>
      <div class="plus-minus-button plus" v-on:click="mpplus()">
        +
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    header: {
      default: undefined,
      type: String
    },
    value: {
      default: 0,
      type: Number
    },
    min: {
      default: 0,
      type: Number
    },
    max: {
      default: undefined,
      type: Number
    },
    step: {
      default: 1,
      type: Number
    },
    inputLabel: {
      required: true,
      type: Number
    },
  },
  data() {
    return {
      newValue: 0
    }
  },
  methods: {
    mpplus: function () {
      if (this.max === undefined || (this.newValue < this.max)) {
        this.newValue = this.newValue + this.step
        this.$emit('input', this.newValue)
      }
    },
    mpminus: function () {
      if ((this.newValue) > this.min) {
        this.newValue = this.newValue - this.step
        this.$emit('input', this.newValue)
      }
    }
  },
  watch: {
    value: {
      handler: function (newVal) {
        this.newValue = newVal
      }
    }
  },
  created: function () {
    this.newValue = this.value
  }
}
</script>
<style scoped>
.plus-minus-input {
  display: flex;
  user-select: none;
  align-items: center;
  justify-content: space-between;
}

.plus-minus-input div {
  display: inline-block;
}

.plus-minus-input #field {
  position: relative;
  width: 150px;
  background: #E5E5E5;
  border: 12px solid #01A0C6;
  border-radius: 16px;
}

.plus-minus-input #field svg.glare {
  position: absolute;
  top: -8px;
  left: -8px;
  width: 12px;
}

.plus-minus-input #field input {
  width: 100%;
  text-align: right;
  font-family: ds-digi, sans-serif;
  font-size: 32px;
  color: #000;
  margin: 8px 0;
  padding: 0 24px 0 0;
  background: transparent;
  border: none;
}

.plus-minus-input #field .input-label {
  font-family: ds-digi, sans-serif;
  font-size: 24px;
  color: #000;
  position: absolute;
  top: 14px;
  right: 6px;
}

.plus-minus-input .plus-minus-button {
  cursor: pointer;
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background: #01A0C6;
  margin: 0 16px;
  font-size: 22px;
  text-align: center;
}

@media only screen and (max-width: 540px) {
  .plus-minus-input { flex-direction: column; }
  h2 { margin-bottom: 16px; }
}

</style>