<template>
  <div id="app">
    <Puzzles @puzzle-changed="selectedPuzzleId = $event" />
    <Records />
    <SliderPuzzle :puzzleId="selectedPuzzleId" />
  </div>
</template>
<script>
import Puzzles from './components/Puzzles'
import Records from './components/Records'
import SliderPuzzle from './components/SliderPuzzle'

export default {
  name: 'App',
  components: { Puzzles, Records, SliderPuzzle },
  data() {
    return {
      selectedPuzzleId: 'cut-pink',
    }
  },
}
</script>

<style>
#app {
}
</style>
