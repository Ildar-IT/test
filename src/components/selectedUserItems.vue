<template>
  <div class="selected-user-items border">
    <div class="selected-user-items__wrapper">
      <div v-for="item in selectedItems" class="border">
        {{item.name}}
      </div>
    </div>
    <p>
      Selected: {{selectedItems.length}} / {{size}}
    </p>
  </div>
</template>

<script>
export default {
  name: "selectedUserItems",
  props:{
    selectedItems: {
      type: Array,
      default: []
    },
    size: {
      type: Number,
      default: 6
    }
  }
}
</script>

<style lang="scss">
.selected-user-items {
  width: 300px;
  min-height: 200px;
  padding: 15px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  &__wrapper {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    & > div {
      margin: 5px;
    }
  }
}
</style>
