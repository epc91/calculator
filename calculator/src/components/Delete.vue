<template>
  <div class="delete">
    <div  v-for="(item, i) in items"
          :key="i"
          :class="{'active': activeItem.includes(i)}"
    >
      <button @click="selectedItem(i)">
        {{ item }}
      </button>
    </div>
      <button @click="randomItem">
        Random
      </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: ['a', 'b', 'c', 'd'],
      activeItem: [],
    }
  },
  methods: {
    selectedItem(i) {
      if(!this.activeItem.includes(i)) {
        this.activeItem.push(i)
      } else {
        let index = this.activeItem.indexOf(i)
        console.log(index);
        this.activeItem.splice(index, 1)
        // if(index > -1) {
        //   console.log(this.activeItem);
        //   this.activeItem.splice(index, 1)
        //   console.log(this.activeItem);
        // }
      }
    },
    randomItem() {
      this.activeItem.push()
    }
  }
}
</script>

<style scoped>
.active {
  background: red;
}
</style>