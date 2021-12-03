<template>
    <div class="addInputContainer">
        <input
          class="addInput"
          type="text"
          v-model="name"
          :placeholder="$t('nom-and-prenom')"
        />
    
        <textarea
          class="addInput"
          type="text"
          v-model="bio"
          :placeholder="$t('biographie')"
        >

        </textarea>

        <input class="addInput" type="button" :value="$t('enregistrer')" @click="createData">
      </div>
</template>

<script>
import axios from "axios";

export default {
    data() {
        return {
            name: '',
            bio: ''
        }
    },
    methods: {
        async createData() {
            let res= await axios.post("https://api.nuit.jiveoff.fr/textes", {"texte": this.bio, "date": new Date()});
            await axios.post("https://api.nuit.jiveoff.fr/personnes", {nom_prenom: this.name, texte: res.data.id});
            window.location.replace("/");
        }
    }
}
</script>

<style>

    .addInputContainer {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .addInput {
        width: 60vw;
        margin: 0 auto;
        max-width: 25em;
        font-size: 24px;
        border: none;
        color:var(--font);
        padding: 0.7em;
        margin: 0.7em;
        background-color: var(--secondary);
        border-radius: 2em;
        cursor: auto;
    }

</style>