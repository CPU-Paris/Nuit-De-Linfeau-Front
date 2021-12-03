<template>
    <div class="admin__ctx">
            <div class="admin__row">
                <smallbox title="Nombre d'élément" value=45></smallbox>
                <smallbox title="En attente d'approbation" value=5></smallbox>
                <smallbox title="En attente d'acceptation" value=45></smallbox>
            </div>
    </div>
</template>

<script>
import smallbox from '../../components/admin/smallbox.vue';

export default {
    components: {smallbox}

}
</script>

<style>

*, *::before, *::after {
    margin: 0;
    padding: 0;
}

.admin__ctx {
    background-color: #045de9;
    background-image: linear-gradient(315deg, #045de9 0%, #09c6f9 74%);
    width: 100%;
    min-height: 100vh;
    height: 100%;
}

.admin__container {

}

.admin__row {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}

</style>