<template>
  <div class="page">
    <div class="nav">
      <ul>
        <li>
          <nuxt-link to="/settings" >General</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/settings/desks">Deck</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/settings/schuedule">Schedule</nuxt-link>
        </li>
      </ul>
    </div>
    <nuxt-child>

    </nuxt-child>
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

