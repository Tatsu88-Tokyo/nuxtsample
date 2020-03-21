<template>
  <div class="container">
    <router-link to="hello">リンク</router-link>
    <div v-on:click="houkai()" class="houkai">崩壊ボタン:{{ count }}</div>
    <div
      v-if="page === true"
      v-bind:class="{hinge: bom}"
      v-on:click="pageSwitch()"
      class="page1 animated flipInX"
    >{{ msg }}</div>
    <div v-if="page === false" v-on:click="pageSwitch()" class="page2">へろーわーるど</div>
  </div>
</template>


<style>
.page1 {
  width: 500px;
  height: 500px;
  background-color: aqua;
}
.page2 {
  width: 500px;
  height: 500px;
  background-color: rgb(255, 0, 21);
}
</style>

<script>
export default {
  data() {
    return {
      msg: "こんにちは",
      page: true,
      bom: false,
      count: null
    };
  },
  methods: {
    pageSwitch() {
      if (this.page === true) {
        this.page = false;
      } else {
        this.page = true;
      }
    },
    houkai() {
      this.count += 1;
      if (this.count === 5) {
        this.bom = true;
      }
    }
  }
};
</script>