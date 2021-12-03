<template>
    <div class="personneSearch">

        <h2>{{name}}</h2>
        <adminMarkdown ref="dest"></adminMarkdown>
        <button @click="editBio">{{$t('enregistrer')}}</button>
    </div>
</template>

<script>
import axios from "axios";
import markdown from '~/components/admin/markdown.vue';

export default {
  components: { markdown },
    data() {
        return {
            id: this.$route.params.id,
            name: '',
            bio: '',
            bioCache: ''
        }
    },
    mounted() {
        axios
            .get("https://api.nuit.jiveoff.fr/personnes/by-id/" + this.id)
            .then((response) => {
                console.log(response)
                this.name = response.data.nom_prenom
                this.bio = response.data.bio
                this.bioCache = response.data.bio
            });
    },
    methods: {
        editBio() {
            axios
                .post("https://api.nuit.jiveoff.fr/texte/modifications/", {texte: this.bioCache, texteModifie: this.$refs.dest.getinput()})
            document.location.href = "/personne/" + this.id;  
        }
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