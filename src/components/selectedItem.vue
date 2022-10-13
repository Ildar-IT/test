<template>
  <div class="selected-item border">
      <h1 v-if="selectedItem">{{ selectedItem.name}}</h1>
      <h1 v-else>Selected Item</h1>
  </div>
</template>

<script>
export default {
  name: "selectedItem",
  props: {
    selectedItem: {
      type: Object,
    }
  }
}
</script>

<style lang="scss">
.selected-item {
  width: 300px;
  min-height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
