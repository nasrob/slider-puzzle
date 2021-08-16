<template>
  <div>
    <h1>Select a Puzzle</h1>
    <div v-for="puz of puzzles" :key="puz.id" class="row">
      <div>
        <img :src="require(`../assets/${puz.image}`)" />
      </div>
      <div>
        <h2>{{ puz.title }}</h2>
      </div>
      <div class="play-button">
        <button @click="selectPuzzle(puz)">Play</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      puzzles: [
        { id: 'cut-pink', image: 'pink.jpg', title: 'Pink Flower' },
        { id: 'cut-purple', image: 'purple.jpg', title: 'Purple Flower' },
        { id: 'cut-red', image: 'red.jpg', title: 'Red Flower' },
      ],
    }
  },
  methods: {
    selectPuzzle(puzzle) {
      this.$$emit('puzzle-changed', puzzle.id)
    },
  },
}
</script>
<style scoped>
.row {
  display: flex;
  max-width: 90vw;
  flex-wrap: wrap;
  justify-content: space-between;
}
.row img {
  width: 100px;
}

.row .play-button {
  padding-top: 25px;
}
</style>
