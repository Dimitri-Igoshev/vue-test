<template>
  <div class="item" @click="$emit('select', item)">
    {{ name }}
  </div>
</template>

<script>
export default {
  name: 'Item',
  props: {
    item: {
      type: Object,
      required: true,
    }
  },
  computed: {
    name() {
      return this.item?.name ? this.item.name : ''
    }
  }
}
</script>

<style scoped>
.item {
  display: flex;
  justify-content: center;
  align-items: center;
  border: .2rem solid teal;
  color: teal;
  padding: 1rem;
  cursor: pointer;
}
</style>
