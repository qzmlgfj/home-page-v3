<template>
  <div class="column">
    <n-h1
      class="animate__animated"
      :class="{ animate__rubberBand: IDIsShaking }"
      @click="IDShaking"
      @animationend="IDRecover"
    >
      Qzmlgfj
    </n-h1>

    <n-h2>Who's this guy</n-h2>
    A lazy dog from a second-rate university, an undergraduate student.

    <n-h2>Interests</n-h2>
    <n-ul>
      <n-li>
        Enjoy creating new projects and repositories, but never finish them.
      </n-li>
      <n-li>Front-end development, just a beginner.</n-li>
      <n-li>Making gadgets.</n-li>
    </n-ul>

    <n-h2>Recent plans</n-h2>
    <n-ul>
      <n-li>Find something interests me.</n-li>
      <n-li>Write some introductory articles about Computer Science.</n-li>
    </n-ul>
  </div>
</template>

<script>

import {NH1, NH2, NUl, NLi} from "naive-ui"

export default {
  name: "Profile",
  components :{
    NH1,
    NH2,
    NUl,
    NLi
  },
  data: function () {
    return {
      IDIsShaking: true,
      shakingTimes: 0,
    };
  },
  methods: {
    IDShaking: function () {
      if (this.shakingTimes >= 10) {
        window.alert("I'm dizzy!!!");
        this.shakingTimes = 0;
      } else {
        this.IDIsShaking = true;
        this.shakingTimes = this.shakingTimes + 1;
      }
    },
    IDRecover: function () {
      this.IDIsShaking = false;
    },
  },
};
</script>

<style scoped>
.column{
  font-family: v-mono;
}
</style>