<template>
  <div id="page" :class="{'black': themeBlack == true}">
    <lang-switch />
    <p>{{ $t('les-sauveteurs-silencieux') }}</p>

    <p>{{ $t("hey") }}</p>
    <HomeSearch></HomeSearch>
    <p>
    </p>
  </div>
</template>

<script>
import langSwitch from "../components/langSwitch.vue";

export default {
  components: { langSwitch },
  data() {
    return {
      counter: 0,
      themeBlack: false
    };
  },
  methods: {
  }
};
</script>

<style>
#page {
  font-size: 1em;
  background-color: #ecabab;
}
#page p {
  color: #555;
}
#page b {
  color: #000;
}

#page.black {
  background-color: #272626;
}
#page.black p {
  color: #d9dad8;
}
#page.black b {
  color: rgb(255, 255, 255);
}

</style>