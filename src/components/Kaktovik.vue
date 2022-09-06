<script>
  import zero from "../assets/kaktovik/0.svg";
  import one from "../assets/kaktovik/1.svg";
  import two from "../assets/kaktovik/2.svg";
  import three from "../assets/kaktovik/3.svg";
  import four from "../assets/kaktovik/4.svg";
  import five from "../assets/kaktovik/5.svg";
  import six from "../assets/kaktovik/6.svg";
  import seven from "../assets/kaktovik/7.svg";
  import eight from "../assets/kaktovik/8.svg";
  import nine from "../assets/kaktovik/9.svg";
  import ten from "../assets/kaktovik/10.svg";
  import eleven from "../assets/kaktovik/11.svg";
  import twelve from "../assets/kaktovik/12.svg";
  import thirteen from "../assets/kaktovik/13.svg";
  import fourteen from "../assets/kaktovik/14.svg";
  import fifteen from "../assets/kaktovik/15.svg";
  import sixteen from "../assets/kaktovik/16.svg";
  import seventeen from "../assets/kaktovik/17.svg";
  import eighteen from "../assets/kaktovik/18.svg";
  import nineteen from "../assets/kaktovik/19.svg";

  const kaktovik = {
    0: zero,
    1: one,
    2: two,
    3: three,
    4: four,
    5: five,
    6: six,
    7: seven,
    8: eight,
    9: nine,
    a: ten,
    b: eleven,
    c: twelve,
    d: thirteen,
    e: fourteen,
    f: fifteen,
    g: sixteen,
    h: seventeen,
    i: eighteen,
    j: nineteen
  }

  export default {
    name: 'kaktovikImg',
    props: {
      number: String
    },
    methods: {
      getKaktovik (num) {
        return kaktovik[num];
      }
    }
  }
</script>

<template>
  <img :src="getKaktovik(number)" />
</template>

<style scoped>
</style>
