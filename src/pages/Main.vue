<template>
  <div class="main">
    <div class="main__wrap">
      <selected-user-items :selectedItems="selectedUserItems" :size="selectedItemsSize"/>
      <selected-item :selectedItem="selectedItem" />
    </div>
    <div class="main__wrap-list">
      <select-list :list="userItems"
                   :type="'user'"
                   @addItem="addItem"
      />
      <select-list :list="selectItems"
                   :type="'item'"
                   @addItem="addItem"
      />
    </div>
  </div>
</template>

<script>
import selectedUserItems from "@/components/selectedUserItems";
import selectedItem from "@/components/selectedItem";
import selectList from "@/components/selectList";


export default {
  name: 'Main',
  components: {
    selectedUserItems,
    selectedItem,
    selectList,
  },
  data() {
    return {
      userItems: [
        {
          id: 1,
          name: "Shoes 1"
        },
        {
          id: 2,
          name: "Shoes 2"
        },
        {
          id: 3,
          name: "Shoes 3"
        },
        {
          id: 4,
          name: "Shoes 4"
        },
        {
          id: 5,
          name: "T-shirt 1"
        },
        {
          id: 6,
          name: "T-shirt 2"
        },
        {
          id: 7,
          name: "T-shirt 3"
        },
        {
          "id": 8,
          name: "T-shirt 4"
        }
      ],
      selectItems: [
        {
          id: 11,
          name: "Jacket 1"
        },
        {
          id: 12,
          name: "Jacket 2"
        },
        {
          id: 13,
          name: "Jacket 3"
        },
        {
          id: 14,
          name: "Jacket 4"
        },
        {
          id: 15,
          name: "Hoodie 1"
        },
        {
          id: 16,
          name: "Hoodie 2"
        },
        {
          id: 17,
          name: "Hoodie 3"
        },
        {
          id: 18,
          name: "Hoodie 4"
        }
      ],
      selectedUserItems: [],
      selectedItem: null,
      selectedItemsSize: 6,
    }
  },
  methods: {
    addItem(item, type) {
      if(type === 'user') {
        if (this.selectedUserItems.length === 6) {
          this.selectedUserItems.pop();
        }
        this.selectedUserItems.unshift(item)
      }

      else if (type === 'item'){
       this.selectedItem = item;
      }
    }
  }
}
</script>

<style lang="scss">
.main {
  &__wrap {
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
    &-list {
      display: grid;
      justify-content: space-between;
      grid-template-columns: 1fr 1fr;
      gap: 20px;
    }
  }
}
</style>
