<template>
  <div class="nuxt_tag" :class="{'dark': darktheme}">
    <header>
      <nuxt-link to="/">
        <logo />
      </nuxt-link>
      <div class="separator"></div>
      <theme-switcher @themeChanged="onThemeChange" />
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
  data () {
    return {
      darktheme: false
    }
  },
  methods: {
    onThemeChange(dtheme) {
      this.darktheme = dtheme;
    }
  }
}
</script>

<style>

:root, .nuxt_tag {
  --primary: #E6DDC4;
  --secondary: #F5F0E0;
  --default: #678983;
  --font: #B3984C;
  --imgFont: #181D31;
  --imgFirstCol: #F87D38;
  --imgSecondCol: #F1F1F1;
}
.nuxt_tag.dark {
  --primary: #864879;
  --secondary: #E9A6A6;
  --default: #3F3351;
  --font: #42243C;
  --imgFont: #1F1D36;
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
}
.nuxt_tag {
  background: var(--primary);
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