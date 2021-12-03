<template>
    <div id="page" class="">
        {{ $t('bonjour') }}
        <div id="text">
            <div id="gradient">

            </div>
        </div>
        <div></div>
    </div>
</template>

<script>

export default {
    setup() {
        
    },
}
</script>

<style>
    #gradient {
        width: 100%;
        height: 100%;
        border: 1px solid red;
        background: linear-gradient(rgb(24, 24, 24), rgba(1,1,1));
    }
</style>