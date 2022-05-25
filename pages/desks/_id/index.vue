<template>
  <div>
    <div class="container">
      <h3>Deck: Learning English</h3>
      <div class="tools">
        <div class="btn btn-success">Start now</div>
        <div class="btn btn-primary" @click.prevent="openModal">
          Creat a card
        </div>
      </div>
      <div class="desk-list">
        <div class="flip-card mt-2">
          <div class="flip-card-inner">
            <div class="flip-card-front">
              <img
                src="img_avatar.png"
                alt="Avatar"
                style="width: 300px; height: 300px"
              />
            </div>
            <div class="flip-card-back">
              <h1>John Doe</h1>
              <p>Architect & Engineer</p>
              <p>We love that guy</p>
            </div>
          </div>
        </div>
        <div class="flip-card mt-2">
          <div class="flip-card-inner">
            <div class="flip-card-front">
              <img
                src="img_avatar.png"
                alt="Avatar"
                style="width: 300px; height: 300px"
              />
            </div>
            <div class="flip-card-back">
              <h1>John Doe</h1>
              <p>Architect & Engineer</p>
              <p>We love that guy</p>
            </div>
          </div>
        </div>
        <div class="flip-card mt-2">
          <div class="flip-card-inner">
            <div class="flip-card-front">
              <img
                src="img_avatar.png"
                alt="Avatar"
                style="width: 300px; height: 300px"
              />
            </div>
            <div class="flip-card-back">
              <h1>John Doe</h1>
              <p>Architect & Engineer</p>
              <p>We love that guy</p>
            </div>
          </div>
        </div>
        <div class="flip-card mt-2">
          <div class="flip-card-inner">
            <div class="flip-card-front">
              <img
                src="img_avatar.png"
                alt="Avatar"
                style="width: 300px; height: 300px"
              />
            </div>
            <div class="flip-card-back">
              <h1>John Doe</h1>
              <p>Architect & Engineer</p>
              <p>We love that guy</p>
            </div>
          </div>
        </div>
        <div class="flip-card mt-2">
          <div class="flip-card-inner">
            <div class="flip-card-front">
              <img
                src="img_avatar.png"
                alt="Avatar"
                style="width: 300px; height: 300px"
              />
            </div>
            <div class="flip-card-back">
              <h1>John Doe</h1>
              <p>Architect & Engineer</p>
              <p>We love that guy</p>
            </div>
          </div>
        </div>
      </div>
      <v-modal name="CreatDeskModal">
        <div class="test-body">
          <h1>Create a new desk</h1>
          <button class="btn btn-danger" @click.prevent="closeModal">X</button>
        </div>
      </v-modal>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DeckInfo',
  validate(context) {
    console.log(context)
    return /^[0-9]$/.test(context.params.id)
  },
  methods: {
    openModal() {
      console.log('12121')
      this.$modal.open({ name: 'CreatDeskModal' })
    },
    closeModal() {
      console.log('12121')
      this.$modal.close({ name: 'CreatDeskModal' })
    },
  },
}
</script>

<style lang="scss">
.flip-card {
  background-color: transparent;
  width: 300px;
  height: 200px;
  border: 1px solid #f1f1f1;
  perspective: 1000px; /* Remove this if you don't want the 3D effect */
}

/* This container is needed to position the front and back side */
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

/* Do an horizontal flip when you move the mouse over the flip box container */
.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

/* Position the front and back side */
.flip-card-front,
.flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden; /* Safari */
  backface-visibility: hidden;
}

/* Style the front side (fallback if image is missing) */
.flip-card-front {
  background-color: #bbb;
  color: black;
}

/* Style the back side */
.flip-card-back {
  background-color: dodgerblue;
  color: white;
  transform: rotateY(180deg);
}

.test-body {
  position: relative;
  background: white;
  padding: 1rem;
  padding-top: 3rem;
}
button.btn.btn-danger {
  position: absolute;
  top: 0;
  right: 0;
}
</style>

