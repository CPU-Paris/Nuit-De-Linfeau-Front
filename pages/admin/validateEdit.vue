<template>
  <div class="container5050 validateEditPage">
    <div class="left-half">
      <list-action v-for="modif of modifs" :key="modif.id" :keyprop="modif.id" :category="modif.category" @btnSelected="btnSelected" @accept="accept" @reject="reject" :showActionButtons="modif.id == selectedModif">
        {{modif.name}}
      </list-action>
    </div>
    <div class="right-half validateDifferences">
      <h2>Differences :</h2>
      <code-diff :old-string="curr" :new-string="next" :context="10" />
    </div>
  </div>
</template>

<script>
import CodeDiff from "vue-code-diff";
import Markdown from '~/components/admin/markdown.vue';
import ListAction from './listAction.vue';
export default {
  components: { CodeDiff, Markdown, ListAction },
  data() {
    return {
      curr: "merci de sélectionner une modif sur le menu latéral",
      next: "",
      modifs: [
        {id: 1, name: "Modif A personnage", category: "buoy", before: "Coucou", after: "coucoue"},
        {id: 2, name: "Modif B évènement", category: "boat", before: "hahahahaha", after: "hahahaha"},
        {id: 3, name: "Modif C évènement", category: "buoy", before: "bonjour", after: "le monde"},
        {id: 4, name: "Modif D évènement", category: "boat", before: "API codée", after: "mais non fonctionnelle :c"},
      ],
      selectedModif: null
    };
  },
  methods: {
    validate() {
      this.curr = this.$refs.source.getinput();
      this.next = this.$refs.dest.getinput();
    },
    btnSelected(e) {
      this.selectedModif = e.keyprop;
      const obj = this.modifs.find(modif => modif.id == e.keyprop);
      this.curr = obj.before;
      this.next = obj.after;
    },
    accept(e) {
      alert("Accept "+e.keyprop);
      this._removeFromArray(e.keyprop);
    },
    reject(e) {
      alert("Reject "+e.keyprop);
      this._removeFromArray(e.keyprop);
    },
    _removeFromArray(keyprop) {
      this.modifs = this.modifs.filter(modif => modif.id != keyprop);
    }
  },
};
</script>

<style>
.validateEditPage {
  background-color: var(--defaultLight);
  border-radius: 2.1em;
  margin: 0 2em;
}
/* Pattern styles */
.container5050 {
  display: grid;
}
.container5050 .left-half {
  grid-column: 1;
}
.container5050 .right-half {
  grid-column: 2;
}
.validateDifferences {
  padding: 0 1em;
}
</style>