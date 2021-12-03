<template>
  <div id="indexpage" :class="{ black: themeBlack == true }">
    <p>{{ $t('home-catchphrase') }}</p>
    <HomeSearch></HomeSearch>
  </div>
</template>

<script>
import langSwitch from "../components/langSwitch.vue";

export default {
  components: { langSwitch },
  data() {
    return {
      counter: 0,
      themeBlack: false,
    };
  },
  methods: {},
};
// todo : remove fontawesome
</script>

<style>
#indexpage {
  font-size: 1em;
}
#indexpage>p {
  color: #678983;
  text-align: center;
  font-weight: 500;
}
</style>