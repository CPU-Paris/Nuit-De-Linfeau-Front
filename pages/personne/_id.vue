<template>
    <div class="personneSearch">

        <h2>{{name}}</h2>

        <p>{{bio === null ? "Vide" : bio.texte}}</p>
    </div>
</template>

<script>
import axios from "axios";

export default {
    data() {
        return {
            id: this.$route.params.id,
            name: '',
            bio: ''
        }
    },
    mounted() {
        axios
            .get("https://api.nuit.jiveoff.fr/personnes/by-id/" + this.id)
            .then((response) => {
                console.log(response)
                this.name = response.data.nom_prenom
                this.bio = response.data.bio
            });
    }
}
</script>

<style>

    .personneSearch {
        width: 90%;
        margin: 0 auto;
        padding: 2rem;
        background-color: var(--default);
        color: var(--secondary);
        border-radius: 16px;
    }

    .personneSearch h2 {
        font-size: 48px;
        margin: 16px
    }

    .personneSearch p {
        font-size: 21px;
        margin: 16px;
    
    }

</style>