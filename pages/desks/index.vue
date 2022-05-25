<template>
  <div>
    <div class="container">
      <ul>
        <li>
          <nuxt-link to="desks/1">
            <div class="card text-white bg-primary">
              <img
                class="card-img-top"
                src="https://media.istockphoto.com/vectors/english-vector-id1047570732?k=20&m=1047570732&s=612x612&w=0&h=fcgzlrNrq_hws1ykrLSpyBVZoIGr54EUueD6WAEVW0c="
                alt=""
              />
              <div class="card-body">
                <h4 class="card-title">Title</h4>
                <p class="card-text">Text</p>
              </div>
            </div>
          </nuxt-link>
        </li>
        <li>
          <nuxt-link to="desks/1">
            <div class="card text-white bg-primary">
              <img
                class="card-img-top"
                src="https://media.istockphoto.com/vectors/english-vector-id1047570732?k=20&m=1047570732&s=612x612&w=0&h=fcgzlrNrq_hws1ykrLSpyBVZoIGr54EUueD6WAEVW0c="
                alt=""
              />
              <div class="card-body">
                <h4 class="card-title">Title</h4>
                <p class="card-text">Text</p>
              </div>
            </div>
          </nuxt-link>
        </li>
        <li>
          <nuxt-link to="desks/1">
            <div class="card text-white bg-primary">
              <img
                class="card-img-top"
                src="https://media.istockphoto.com/vectors/english-vector-id1047570732?k=20&m=1047570732&s=612x612&w=0&h=fcgzlrNrq_hws1ykrLSpyBVZoIGr54EUueD6WAEVW0c="
                alt=""
              />
              <div class="card-body">
                <h4 class="card-title">Title</h4>
                <p class="card-text">Text</p>
              </div>
            </div>
          </nuxt-link>
        </li>
        <li>
          <nuxt-link to="desks/1">
            <div class="card text-white bg-primary">
              <img
                class="card-img-top"
                src="https://media.istockphoto.com/vectors/english-vector-id1047570732?k=20&m=1047570732&s=612x612&w=0&h=fcgzlrNrq_hws1ykrLSpyBVZoIGr54EUueD6WAEVW0c="
                alt=""
              />
              <div class="card-body">
                <h4 class="card-title">Title</h4>
                <p class="card-text">Text</p>
              </div>
            </div>
          </nuxt-link>
        </li>

        <li>
          <nuxt-link to="desks/1">
            <div class="card text-white bg-primary">
              <img
                class="card-img-top"
                src="https://media.istockphoto.com/vectors/english-vector-id1047570732?k=20&m=1047570732&s=612x612&w=0&h=fcgzlrNrq_hws1ykrLSpyBVZoIGr54EUueD6WAEVW0c="
                alt=""
              />
              <div class="card-body">
                <h4 class="card-title">Title</h4>
                <p class="card-text">Text</p>
              </div>
            </div>
          </nuxt-link>
        </li>
        <li>
          <nuxt-link to="desks/1">
            <div class="card text-white bg-primary">
              <img
                class="card-img-top"
                src="https://media.istockphoto.com/vectors/english-vector-id1047570732?k=20&m=1047570732&s=612x612&w=0&h=fcgzlrNrq_hws1ykrLSpyBVZoIGr54EUueD6WAEVW0c="
                alt=""
              />
              <div class="card-body">
                <h4 class="card-title">Title</h4>
                <p class="card-text">Text</p>
              </div>
            </div>
          </nuxt-link>
        </li>
        <li>
          <nuxt-link to="desks/1">
            <div class="card text-white bg-primary">
              <img
                class="card-img-top"
                src="https://media.istockphoto.com/vectors/english-vector-id1047570732?k=20&m=1047570732&s=612x612&w=0&h=fcgzlrNrq_hws1ykrLSpyBVZoIGr54EUueD6WAEVW0c="
                alt=""
              />
              <div class="card-body">
                <h4 class="card-title">Title</h4>
                <p class="card-text">Text</p>
              </div>
            </div>
          </nuxt-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DeskIndex',
  layout: 'default',
  data() {
    return {
      deckID: '1',
    }
  },
  methods: {
    showDeck() {
      this.$router.push(`/desks/${this.deckID}`)
    },
  },
}
</script>

<style lang="scss">
ul {
  margin: 0;
  padding: 0;
  display: flex;

  li {
    margin: 10px 10px;
    list-style: none;
  }
}
</style>

