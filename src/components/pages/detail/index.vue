<template>
  <div>
    <h1>This is Detail Page!!</h1>
    <ul>
      <li class="detail-item" v-for="list in lists" :key="list.id" @click="move(list.id)">
        <span>{{list.id}} {{list.name}}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lists: [
        { id: "001", name: "Aさん" },
        { id: "002", name: "Bさん" },
        { id: "003", name: "Cさん" },
        { id: "004", name: "Dさん" },
        { id: "005", name: "Eさん" }
      ]
    };
  },
  methods: {
    move(id) {
      this.$router.push(`/detail/${id}`);
    }
  }
};
</script>

<style>
.detail-item {
  cursor: pointer;
  line-height: 40px;
}
.detail-item > span {
  text-decoration: underline;
}
.detail-item > span:hover {
  opacity: 0.8;
}
</style>
