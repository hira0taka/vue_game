<template>
  <div class="text-center border border-info my-1 px-2">
    <p v-on:click="doAction">{{ ans }}</p>
  </div>
</template>

<script>
export default {
  name: "Ans",
  props: {
    ans: String,
  },
  methods: {
      doAction() {
          // thisは「このコンポーネントにある」
         if(this.ans === "WHITE"){
             console.log("正解")
            //  「this.ans = "正解"」はエラー。propsの値を直接変更はできない。
         } else {
             console.log("不正解")
         }
      }
  }
};
</script>
