<template>
  <div class="main">
    <h1>{{ items.length }}</h1>
    <div class="box-view">
      <Box
        v-for="(name, index) in items"
        :key="index" :text="name"
      />
      <div class="add-box" @click="addItem">+</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [],
      fruits: [
        "Apple", "Apricot", "Avocado", "Banana", "Blackberry", "Blueberry",
        "Cherry", "Coconut", "Cucumber", "Durian", "Dragonfruit", "Fig",
        "Gooseberry", "Grape", "Guava", "Jackfruit", "Plum", "Kiwifruit",
        "Kumquat", "Lemon", "Lime", "Mango", "Watermelon", "Mulberry",
        "Orange", "Papaya", "Passionfruit", "Peach", "Pear", "Persimmon",
        "Pineapple", "Pineberry", "Quince", "Raspberry", "Soursop",
        "Strawberry", "Tamarind", "Yuzu"
      ]
    }
  },
  methods: {
    makeId() {
      let id = ''
      for (let i = 0; i < 2; i++) {
        id += this.fruits[Math.floor(Math.random() * this.fruits.length)]
      }
      return id
    },
    addItem() {
      this.items.push(this.makeId())
    }
  }
}
</script>

<style>
.main {
  margin: 0 auto;
  padding-top: 1rem;
  min-height: 100vh;
  background: #eeeeee;
  text-align: center;
  user-select: none;
}

.box-view {
  padding: 3rem;
  display: grid;
  grid-gap: 1.5rem;
  place-items: center;
  grid-template-rows: repeat(auto-fill, minmax(10rem, 1fr));
  grid-template-columns: repeat(auto-fill, minmax(10rem, 1fr));
}

.add-box {
  width: 10rem;
  height: 10rem;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 10%;
  border: 5px dashed black;
  font-weight: bold;
  font-size: 7rem;
  cursor: pointer;
}
</style>
