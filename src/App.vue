<template>
  <div id="app">
    <search v-model="searchQuery" />
    <item-list :items="filteredItems" />
  </div>
</template>

<script>
import Search from "./components/Search.vue";
import ItemList from "./components/ItemList.vue";

export default {
  name: "app",
  components: {
    Search,
    ItemList
  },
  mounted() {
    fetch("http://localhost:3000/items").then(async res => {
      this.items = await res.json();
    });
  },
  data() {
    return {
      items: [],
      searchQuery: ""
    };
  },
  computed: {
    filteredItems() {
      return this.items.filter(
        item => item.name.indexOf(this.searchQuery) !== -1
      );
    }
  }
};
</script>

<style>
body {
  display: flex;
  justify-content: center;
}
</style>

<style scoped>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 50%;
}
</style>
