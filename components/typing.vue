<template>
  <span>{{ getText }}</span>
</template>

<script>
export default {
    data() {
        return {
            progress: 0
        }
    },
    props: {
        text: {
            type: String,
            required: true
        },
        speed: {
            type: Number,
            required: false,
            default: 80
        },
        startAfter: {
            type: Number,
            required: false,
            default: 0
        }
    },
    computed: {
      getText() {
        return this.text.substring(0, this.progress);
      }
    },
    methods: {
      typingAnimation() {
        if (this.progress < this.text.length) {
          this.progress++;
          setTimeout(this.typingAnimation, this.speed);
        }
      }
    },
    mounted() {
        setTimeout(this.typingAnimation, this.startAfter);
    }
}
</script>

<style>

</style>