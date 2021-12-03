<template>
  
    <div class="smallbox__ctx">
        <h2 class="smallbox__title">
            {{title}}
        </h2>
        <h3 class="smallbox__value">
            {{+value}}
        </h3>
    </div>

</template>

<script>
export default {
    props: {
        title: {
            type: String,
            default: 'No title provided'
        },
        value: {
            type: String,
            default: "-1"
        }
    }

}
</script>

<style>

.smallbox__ctx {
    background: rgba(255,255,255,0.4);
    border-radius: 10px;
    border: 1px solid rgba(255,255,255,0.2);
    position: absolute;
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
    display: block;
    margin: 0 auto;
}

</style>