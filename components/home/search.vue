<template>
  <div class="searchComponent">
    <input
      class="searchInput"
      type="text"
      v-model="search"
      @input="fetchInput"
      :placeholder="$t('recherche')"
    />
    <ul>
      <li v-for="item in result" :key="item.id">
        <a :href="'/personne/' + item.id">{{ item.nom_prenom }}</a>
      </li>
    </ul>

    <a class="addComponent" href="/personne/add">
      <img src="/img/reject.svg" :alt="$t('reject-svg')">
    </a>
  </div>
</template>

<script>
import modal from "../modal.vue";
import axios from "axios";
export default {
  components: { modal },
  data() {
    return {
      search: "",
      result: [],
    };
  },
  methods: {
    fetchInput() {
      if (!this.search) {
        this.result = [];
        return;
      }

      axios
        .get("https://api.nuit.jiveoff.fr/personnes/" + this.search)
        .then((response) => {
            console.log(response)
            this.result = [...response.data];
            this.result.length = this.result.length > 4 ? 4 : this.result.length;
        });

        axios
        .get("https://api.nuit.jiveoff.fr/bateaux/" + this.search)
        .then((response) => {
            console.log(response)
            this.result = [...this.result, ...response.data];
            this.result.length = this.result.length > 4 ? 4 : this.result.length;
        });
      
    },
  },
};
</script>

<style>

.searchComponent {
  display: flex;
  justify-content: center;
  width: fit-content;
  position: relative;
  margin: 0 auto;
}

.searchComponent .searchInput {
  width: 60vw;
  max-width: 25em;
  font-size: 24px;
  border: none;
  color:var(--font);
  padding: 0.7em;
  margin: 0.7em;
  background-color: var(--secondary);
  border-radius: 2em;
}

.searchComponent ul {
  position: absolute;
  top: 70%;
  width: 100%;
  padding: 0;
  background-color: var(--default);
  border-radius: 32px;
}

.searchComponent ul li {
    list-style: none;
}

.searchComponent ul li a {
    display:block;

    border-radius: 32px;
    margin: 8px;
    padding: 16px 8px 16px 32px;
    font-size: 24px;
    color: var(--font);
    background-color: var(--secondary);
    text-decoration: none;
}

.addComponent {
  transform: scale(.5) rotate(45deg);

}
</style>