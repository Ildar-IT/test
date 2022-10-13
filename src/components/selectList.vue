<template>
  <div class="select-list border">
    <div class="select-list__wrap">
      <div  v-for="item in list" :key="item.id"
            class="border"
            @click="addItem(item)">
        {{item.name}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "selectList",
  props: {
    list: {
      type: Array,
      default: []
    },
    type: {
      type: String,
    }
  },
  methods: {
    addItem(item) {
      this.$emit('addItem', item, this.type)
    }
  }
}
</script>

<style lang="scss">
.select-list {

  min-height: 400px;
  padding: 15px;
  &__wrap {
    display: flex;
    flex-wrap: wrap;
    & > div {
      margin: 5px;
      cursor: pointer;
      transition: 0.2s ease-in-out;
      &:hover {
        opacity: 0.7;
      }
    }
  }
}
</style>
