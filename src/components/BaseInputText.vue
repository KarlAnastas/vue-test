<template>
  <input type="text" class="input" :value="value" v-on="listeners">
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      default: '',
    }
  },
  computed: {
    listeners () {
      return {
        //pass all component listeners directly to input
        ...this.$listeners,
        // Override input listener to word with v-model
        input: event => this.$emit('input', event.target.value)
      }
    }
  }
}
</script>

<style lang="scss">
@import '../variables.scss';

.input {
  border: 1px solid $vue-blue;
  padding: 8px 10px;
  width: 100%;
}
</style>

