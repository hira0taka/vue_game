<template>
  <div>
    <div class="board" v-on:click="checkAction">
      <Cell
        v-bind:count="count"
        v-for="(_, id) in cells"
        v-bind:key="id"
        v-bind:number="id"
        v-on:count-event="doCountUp"
      />
    </div>
    <p class="message">{{ message }}</p>
  </div>
</template>

<script>
import Cell from "./Cell.vue";

export default {
  name: "Board",
  components: {
    Cell,
  },
  data() {
    return {
      cells: [0, 0, 0, 0, 0, 0, 0, 0, 0],
      count: 0,
      message: "",
    };
  },
  methods: {
    makeArrays(array) {
      const columnA = [array[0], array[3], array[6]];
      const columnB = [array[1], array[4], array[7]];
      const columnC = [array[2], array[5], array[8]];

      const rowA = [array[0], array[1], array[2]];
      const rowB = [array[3], array[4], array[5]];
      const rowC = [array[6], array[7], array[8]];

      const diagonalA = [array[0], array[4], array[8]];
      const diagonalB = [array[2], array[4], array[6]];

      return [
        columnA,
        columnB,
        columnC,
        rowA,
        rowB,
        rowC,
        diagonalA,
        diagonalB,
      ];
    },
    checkWin(array){
      if(array.every(id => id === "〇")){
        this.message = "Aの勝ち！"
      } else if (array.every(id => id === "×")){
        this.message = "Bの勝ち！"
      }
    },
    doCountUp(clickNumber, cell) {
      this.count++;
      this.cells[clickNumber - 1] = cell;

      const checkArrays = this.makeArrays(this.cells);
      checkArrays.map((array) => this.checkWin(array))
    },
  },
};
</script>

<style>
.board {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  height: 318px;
  width: 318px;
  border: 3px solid black;
}
</style>