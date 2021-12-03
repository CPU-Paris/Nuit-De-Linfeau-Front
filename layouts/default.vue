<template>
  <div class="nuxt_tag">
    <header>
      <nuxt-link to="/">
        <logo />
      </nuxt-link>
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

:root {

  --primaryLight: #E6DDC4;
  --secondaryLight: #F5F0E0;
  --defaultLight: #678983;
  --fontLight: #B3984C;
  --imgFontLight: #181D31;
  --imgFirstCol: #F87D38;
  --imgSecondCol: #F1F1F1;

  --primaryDark: #864879;
  --secondaryDark: #E9A6A6;
  --defaultDark: #3F3351;
  --fontDark: #42243C;
  --imgFontDark: #1F1D36;
  --imgFirstCol: #D55A15;
  --imgSecondCol: #DCDCDC;

}

body {
  margin: 0;
}
#__layout {
    font-family: 'Roboto', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    display: flex;
    width: 100%;
    min-height: 100vh;
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
header .logoDunkerque {
  width: auto;
  height: 100%;
}
header>.separator {
  flex-grow: 1;
}

</style>