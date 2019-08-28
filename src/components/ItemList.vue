<template>
  <ul>
    <li :key="item.id" v-for="item in items">
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