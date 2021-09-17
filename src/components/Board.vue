<template>
  <div class="board" v-on:click="checkAction">
    <Cell
      v-bind:count="count"
      v-for="(_, id) in cells"
      v-bind:key="id"
      v-bind:number="id"
      v-on:count-event="doCountUp"
    />
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
    };
  },
  methods: {
    doCountUp() {
      this.count++;
    }
  },
    methods: {
      checkAction() {
columnA = [cells[0],cells[3],cells[6]]
columnB = [cells[1],cells[4],cells[7]]
columnC = [cells[2],cells[5],cells[8]]

rowA = [cells[0],cells[1],cells[2]]
rowA = [cells[3],cells[4],cells[5]]
rowA = [cells[6],cells[7],cells[8]]


      }
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