<template>
  <div>
      <h2>Source :</h2>
    <adminMarkdown ref="source"></adminMarkdown>
      <h2>Destination :</h2>
    <adminMarkdown ref="dest"></adminMarkdown>
    <p>
    <button @click="validate">Update</button>
    </p>
    <hr>
      <h2>Result :</h2>
    <code-diff :old-string="curr" :new-string="next" :context="10" />
    <hr>
    <h2>compiled: </h2>
    <adminMarkdown v-if="next" :md="next" noEdit></adminMarkdown>
  </div>
</template>

<script>
import CodeDiff from "vue-code-diff";
import Markdown from '~/components/admin/markdown.vue';
export default {
  components: { CodeDiff, Markdown },
  data() {
    return {
      curr: "",
      next: "",
    };
  },
  methods: {
    validate() {
      this.curr = this.$refs.source.getinput();
      this.next = this.$refs.dest.getinput();
    },
  },
};
</script>

<style>
</style>