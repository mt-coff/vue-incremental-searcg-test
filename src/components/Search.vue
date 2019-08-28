<template>
  <input :v-bind="$attrs" :value="value" @input="input" />
</template>

<script>
export default {
  name: "Search",
  props: {
    value: {}
  },
  methods: {
    input(event) {
      this.$emit("input", event.target.value);
    }
  }
};
</script>

<style scoped>
input {
  border: solid 1px #000;
}
</style>