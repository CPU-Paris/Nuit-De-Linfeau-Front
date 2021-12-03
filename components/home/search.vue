<template>
  <div>
      <input type="text" v-model="search">
      <modal ref="resultModal">
          Vous avez entré : {{search}}
      </modal>
      <button @click="showModal">show modal</button>
      

      <div>
          résultat : 
            <ul>
                <li v-for="item in result" :key="item.id">
                    {{item.name}}
                </li>
            </ul>
      </div>
  </div>
</template>

<script>
import modal from '../modal.vue'
export default {
  components: { modal },
    data() {
        return {
            search: 'aa',
            result: [
                {
                    id: 1,
                    name: 'aa'
                },
                {
                    id: 2,
                    name: 'bb'
                }
            ]
        }
    },
    fetch() {
        /*this.$http.get('/api/search/' + this.search).then(response => {
            this.result = response.data
        })*/
    },
    methods: {
        showModal() {
            this.$refs.resultModal.show();
        }
    }
}
</script>

<style>

</style>