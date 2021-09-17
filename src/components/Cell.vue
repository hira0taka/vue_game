<template>
  <div class="cell" v-on:click="doAction">
    {{ cell }}
  </div>
</template>

<script>
export default {
  name: "Cell",
  data() {
    return {
      cell: "",
    };
  },
  props: {
    count: Number,
    number: Number,
  },
  methods: {
    doAction() {
      // 同じところはクリックできない
      if (this.cell === "") {
        if (count % 2 === 0) {
          this.cell = "〇";
          this.$emit("count-event");
        } else {
          this.cell = "×";
          this.$emit("count-event");
        }
      }
    },
  },
};
</script>

<style>
.cell {
  height: 100px;
  width: 100px;
  line-height: 100px;
  border: 3px solid black;
  font-size: 40px;
  font-weight: bolder;
  text-align: center;
}
</style>