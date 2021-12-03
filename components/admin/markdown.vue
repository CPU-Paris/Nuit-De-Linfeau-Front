<template>
    <div class="markdownEditor" :class="{'noEdit':noEdit}">
      <textarea v-if="!noEdit" :value="input" @input="update"></textarea>
      <div v-html="compiledMarkdown"></div>
    </div>
</template>

<script>
import {marked} from 'marked';
export default {
    data() {
        return {
            input: ""
        }
    },
    props: {
        noEdit: {
            type: Boolean,
            default: false
        },
        md: {
            type: String,
            default: "## type your markdown here"
        }
    },
    mounted() {
        this.input = this.md;
    },
    computed: {
        compiledMarkdown() {
            return marked((this.noEdit) ? this.md : this.input, { sanitize: true });
        }
    },
    methods: {
        update(e) {
            this.input = e.target.value;
        },
        getinput() {
            return this.input;
        }
    }
}
</script>

<style>

.markdownEditor>* {
  display: inline-block;
  width: 49%;
  height: 100%;
  vertical-align: top;
  box-sizing: border-box;
  padding: 0 20px;
}
.markdownEditor.noEdit>* {
    
  width: initial;
}

.markdownEditor textarea {
  border: none;
  border-right: 1px solid #ccc;
  resize: none;
  outline: none;
  background-color: #f6f6f6;
  font-size: 14px;
  padding: 20px;
}

.markdownEditor code {
  color: #f66;
}
</style>