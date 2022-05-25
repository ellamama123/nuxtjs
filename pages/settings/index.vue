<template>
  <div class="page">
    <div class="main">
      General setting ....
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      deckID: '1'
    }
  },
  methods: {
    showDeck() {
      this.$router.push(`/desks/${this.deckID}`)
    }
  }
}
</script>

<style scoped lang="scss">
  .page {
    display: flex;
  }
</style>

