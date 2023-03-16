<template>
  <div class="container">
    <div class="wrapper">
      <div class="left-block">
        <Item
          class="item"
          v-for="item in selectedUsersClothes"
          :key="item.id"
          :item="item"
          @select="selectUserClothes"
        />
      </div>
      <div class="right-block">
        <Item
          v-if="selectedClothes"
          class="item"
          :item="selectedClothes"
        />
      </div>
    </div>
    <div class="list-wrapper">
      <div class="left-list">
        <Item
          class="item"
          v-for="item in usersClothes"
          :key="item.id"
          :item="item"
          @select="selectUserClothes"
        />
      </div>
      <div class="right-list">
        <Item
          class="item"
          v-for="item in usersClothes"
          :key="item.id"
          :item="item"
          @select="selectClothes"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Item from './components/Item.vue'
export default {
  components: { Item },
  data() {
    return {
      usersClothes: [
        { "id": 1, "name": "Shoes 1" },
        { "id": 2, "name": "Shoes 2"},
        { "id": 3, "name": "Shoes 3" },
        { "id": 4, "name": "Shoes 4" },
        { "id": 5, "name": "T-shirt 1" },
        { "id": 6, "name": "T-shirt 2" },
        { "id": 7, "name": "T-shirt 3" },
        { "id": 8, "name": "T-shirt 4" }
      ],
      clothes: [
        { "id": 11, "name": "Jacket 1" },
        { "id": 12, "name": "Jacket 2" },
        { "id": 13, "name": "Jacket 3" },
        { "id": 14, "name": "Jacket 4" },
        { "id": 15, "name": "Hoodie 1" },
        { "id": 16, "name": "Hoodie 2" },
        { "id": 17, "name": "Hoodie 3" },
        { "id": 18, "name": "Hoodie 4" }
      ],
      selectedUsersClothes: [],
      selectedClothes: null
    }
  },
  methods: {
    selectUserClothes(item) {
      if (this.selectedUsersClothes.includes(item)) return

      this.selectedUsersClothes.push(item)
    },
    selectClothes(item) {
      this.selectedClothes = item
    }
  }
}
</script>

<style scoped>
.container {
  width: 100%;
  display: flex;
  justify-content: center;
  flex-direction: column;
}
.wrapper {
  display: flex;
  flex-direction: row;
  justify-content: space-between;

}
.left-block {
  margin: 3rem;
  padding: 2rem;
  border: .2rem solid teal;
  width: 40%;
}
.right-block {
  margin: 3rem;
  padding: 2rem;
  border: .2rem solid teal;
  width: 40%;
}
.list-wrapper {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.left-list {
  margin: 3rem;
  padding: 2rem;
  border: .2rem solid teal;
  width: 45%;
}
.right-list {
  margin: 3rem;
  padding: 2rem;
  border: .2rem solid teal;
  width: 45%;
}
.item:not(:first-child) {
  margin-top: 1rem;
}
</style>
