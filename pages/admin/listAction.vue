<template>
  <a href="#!" @click="selectBtn" class="listActionComponent" :class="{'selected': showActionButtons}">
      <div>
        <slot />
      </div>
      <div class="actionIcons">
          <img @click="accept" class="acceptRejectBtn" src="/img/accept.svg" alt="accept"/>
          <img @click="reject" class="acceptRejectBtn" src="/img/reject.svg" alt="reject"/>
          <img :src="category === 'boat' ? '/img/boat.svg' : '/img/buoy.svg'" :alt="category" class="category"/>
      </div>
  </a>
</template>

<script>
export default {
    data() {
        return {
        }
    },
    props: {
        category: {
            type: String,
            required: true
        },
        showActionButtons: {
            type: Boolean,
            required: false,
            default: false
        },
        keyprop: {
            type: Number,
            required: true
        }
    },
    methods: {
        selectBtn() {
            this.$emit('btnSelected', this);
        },
        unselectbtn(uid) {
        },
        accept() {
            this.$emit('accept', this);
        },
        reject() {
            this.$emit('reject', this);
        }
    }
}
</script>

<style>
.listActionComponent {
    display: flex;
    justify-content: space-between;
    height: 2em;
    line-height: 2em;
    padding: 0.1em 1em;
    margin: 1em;
    border-radius: 2em;
    background: var(--secondaryLight);
    color: var(--fontLight);
    text-decoration: none;
}
.listActionComponent img {
    width: 1.5em;
    height: 1.5em;
    margin-right: 0.4em;
}
.acceptRejectBtn {
    display: none;
}
.listActionComponent.selected {
    background: var(--primaryLight);
}
.listActionComponent.selected .acceptRejectBtn {
    display: block;
}
.actionIcons {
    display: flex;
    align-items: center;
}
</style>