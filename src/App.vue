<template>
  <CardsFollowers :darkmode="darkMode" @customChange="logChange" />
  <Overview :class="darkMode === true ? 'night' : ''" />
</template>

<script>
import CardsFollowers from './components/CardsFollowers.vue';
import Overview from './components/Overview.vue';
export default {
  components: {
    CardsFollowers,
    Overview,
  },

  data() {
    return {
      darkMode: false,
    }
  },

  methods: {
    logChange(e) {
      this.darkMode = !this.darkMode;
    }
  }
}
</script>

<style>
:root {
  --ff: 'Inter', sans-serif;

  /* Primary */
  --clr-LimeGreen: hsl(163, 72%, 41%);
  --clr-BrightRed: hsl(356, 69%, 56%);
  --clr-Facebook: hsl(208, 92%, 53%);
  --clr-Twitter: hsl(203, 89%, 53%);
  --clr-Instagram: linear-gradient(#fdc468, #df4996);
  --clr-youTube: hsl(348, 97%, 39%);

  /* Toggle */
  --tg-dark: linear-gradient(hsl(210, 78%, 56%) to hsl(146, 68%, 55%));
  --tg-white: hsl(230, 22%, 74%);

  /* BackgroundColor */

  /* Black Theme */
  --bg-VeryDarkBlue: hsl(231, 26%, 15%);
  --bg-VeryMediumBlue: hsl(232, 19%, 15%);
  --bg-DarkDesaturatedBlue: hsl(228, 28%, 20%);
  --bg-DesaturatedBlue: hsl(228, 34%, 66%);
  --bg-White: hsl(0, 0%, 100%);

  /* Light Theme */
  --bg-White: hsl(0, 0%, 100%);
  --bg-VeryPaleBlue: hsl(225, 100%, 98%);
  --bg-LightGrayishBlue: hsl(227, 47%, 96%);
  --bg-DarkGrayishBlue: hsl(228, 12%, 44%);
  --bg-VeryDarkBlue: hsl(230, 17%, 14%);
}
</style>