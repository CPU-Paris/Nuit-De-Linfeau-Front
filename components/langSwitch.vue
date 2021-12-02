<template>
  <div class="langSwitch">
    <span>Langue :</span>
    <nuxt-link :class="{'disabled': $i18n.locale != 'en'}" :to="switchLocalePath('en')">
        <img class="langFlag" src="/img/EN_lang.svg" alt="English" />
    </nuxt-link>
    <nuxt-link :class="{'disabled': $i18n.locale != 'fr'}" :to="switchLocalePath('fr')">
        <img class="langFlag" src="/img/FR_lang.svg" alt="French" />
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
    display: flex;
    justify-content: center;
    align-items: center;
}
.langSwitch span {
    line-height: 2em;
}
.langSwitch a {
    display: flex;
}
.langFlag {
    height: 2em;
    transition: all 0.2s ease-in-out;
}
.disabled .langFlag {
    transform: scale(0.8);
}
</style>