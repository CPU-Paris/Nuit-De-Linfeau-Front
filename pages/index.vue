<template>
<div>
    <lang-switch />
  <p> {{ $t('hey') }} </p>
  </div>
</template>

<script>
import langSwitch from "../components/langSwitch.vue";

export default {
  components: { langSwitch }
}
</script>

<style>

</style>