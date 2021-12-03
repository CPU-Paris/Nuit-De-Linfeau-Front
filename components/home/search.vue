<template>
  <div class="searchComponent">
    <input
      class="searchInput"
      type="text"
      v-model="search"
      @input="fetchInput"
      placeholder="Recherche..."
    />
    <ul>
      <li v-for="item in result" :key="item.id">
        <a href="">{{ item.nom_prenom }}</a>
      </li>
    </ul>
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
    },
  },
};
</script>

<style>

.searchComponent {
  display: flex;
  justify-content: center;
}

.searchComponent .searchInput {
  width: 60vw;
  max-width: 25em;
  font-size: 24px;
  border: none;
  color: #b3984c;
  padding: 0.7em;
  margin: 0.7em;
  background-color: #f5f0e0;
  border-radius: 2em;
}

.searchComponent ul {
  position: absolute;
  top: 70%;
  left: 20px;
  width: 110%;
  padding: 0;
  background-color: #678983;
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
    color: #b3984c;
    background-color: #f5f0e0;
    text-decoration: none;
}
</style>