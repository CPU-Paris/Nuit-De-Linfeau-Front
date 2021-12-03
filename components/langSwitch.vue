<template>
  <div class="langSwitch">
    <nuxt-link :class="{'disabled': $i18n.locale != 'en'}" :to="switchLocalePath('fr')">
        <img class="langFlag" src="/img/EN_lang.svg" :alt="$t('english')" />
    </nuxt-link>
    <nuxt-link :class="{'disabled': $i18n.locale != 'fr'}" :to="switchLocalePath('en')">
        <img class="langFlag" src="/img/FR_lang.svg" :alt="$t('french')" />
    </nuxt-link>
  </div>
</template>

<script>
export default {
    name: 'langSwitch'
}
</script>

<style>
.langSwitch {
    display: block;
    justify-content: center;
    align-items: center;
    position: relative;
}
.langSwitch span {
    line-height: 5em;
}
.langSwitch a {
    display: flex;
    position: relative;
    top:0;
    left:0;
    z-index: 2;
    opacity: 1;
    transition: all 0.2s ease-in-out;
}
.langFlag {
    height: 5em;
}
.langSwitch a.disabled {
    position: absolute;
    z-index: 1;
    transform: scale(0.8);
    opacity: 0.5;
}
</style>