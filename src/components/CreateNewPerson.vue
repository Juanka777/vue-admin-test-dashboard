<template>
  <div class="modal" :class="{ 'is-active': isActive }">
      <div class="modal-background has-background-white" @click="closeModal()"></div>
      <div class="modal-content has-text-centered">
          <div class="title is-spaced is-1 is-size-1-mobile has-text-centered">Nice!</div>
          <div class="subtitle is-5 is-size-6-mobile">This opens just by adding the <code>is-active</code> to the modal div.</div>
          <hr>
          <span class="tag has-text-grey">Use the button on the top right corner to close.</span>
      </div>
      <button class="modal-close is-large" aria-label="close" @click="closeModal()"></button>
  </div>
</template>

<script>

export default {
  props: {
    isActive: Boolean
  },

  methods:
  {
    closeModal () {
      this.$emit('update:isActive', false)
    }
  }
}
</script>
