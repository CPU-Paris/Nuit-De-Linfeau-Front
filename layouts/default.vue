<template>
  <div class="nuxt_tag">
    <header>
      <logo />
      <div class="separator"></div>
      <theme-switcher />
      <lang-switch />
    </header>
    <div id="anchorimg">
      <img src="/img/anchor.svg" alt="random image" />
    </div>
    <Nuxt/>
  </div>
</template>

<script>
import themeSwitcher from '~/components/layout/theme-switcher.vue'
export default {
  components: { themeSwitcher },
}
</script>

<style>
body {
  margin: 0;
}
#__layout {
    font-family: 'Roboto', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    display: flex;
    width: 100%;
    height: 100vh;
    background: #E6DDC4;
}
.nuxt_tag {
  flex-grow: 1;
  padding: 1em;
}

#anchorimg {
  text-align: center;
}
#anchorimg>img {
  height: 8.5em;
  width: auto;
}

header {
  height: 7em;
  display: flex;
}
header>.logoDunkerque {
  width: auto;
  height: 100%;
}
header>.separator {
  flex-grow: 1;
}

</style>