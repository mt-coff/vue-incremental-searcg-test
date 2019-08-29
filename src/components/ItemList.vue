<template>
  <ul>
    <li :key="item.id" v-for="item in items" @click="handleClick(item)">
      {{ item.name }}
    </li>
  </ul>
</template>

<script>
export default {
  name: "ItemList",
  props: {
    items: {
      type: Array,
      default: () => []
    }
  },
  methods: {
    handleClick(item) {
      this.$emit("click", item);
    }
  }
};
</script>

<style scoped>
li {
  list-style-type: none;
  width: 200px;
  text-align: left;
}
</style>