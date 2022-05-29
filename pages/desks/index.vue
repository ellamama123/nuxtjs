<template>
  <div>
    <div class="container">
      <button class="btn btn-success" @click.prevent="openModal">
        Create new desk
      </button>
      <ul>
        <deck-list
          v-for="deck in decks"
          :id="deck._id"
          :key="deck._id"
          :title="deck.title"
          :des="deck.des"
          :thumbnail="deck.thumbnail"
        />
      </ul>
    </div>
    <v-modal name="CreatDeskModal">
      <div class="test-body">
        <h2>Create a new desk</h2>
        <form action="#">
          <div class="form-group">
            <label for="">Name</label>
            <input
              type="text"
              class="form-control"
              placeholder="Enter name...."
            />
          </div>
          <div class="form-group">
            <label for="">Description</label>
            <textarea
              type="text"
              class="form-control"
              placeholder="Enter description...."
            />
          </div>
          <div class="form-group">
            <label for="">Image</label>
            <input
              type="file"
              class="form-control"
              placeholder="File here...."
            />
            <div class="preview"></div>
          </div>
        </form>
        <div class="d-flex justify-content-end mt-3">
          <button class="btn btn-success mr-3">Create a Desk</button>
          <button class="btn btn-danger" @click.prevent="closeModal">
            Close
          </button>
        </div>
      </div>
    </v-modal>
  </div>
</template>

<script>
import DeckList from '@/components/Decks/DeckList.vue'
export default {
  name: 'DeskIndex',
  layout: 'default',
  components: { DeckList },
  data() {
    return {
      deckID: '1',
    }
  },
  asyncData(context, callback) {
    console.log('hello')
    // eslint-disable-next-line
    setTimeout(() => {
      callback(null, {
        decks: [
          {
            _id: '1',
            thumbnail:
              'https://dangkyduhoc.vn/wp-content/uploads/2021/04/52351011-english-british-england-language-education-concept.jpg',
            title: 'English',
            des: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to ma",
          },
          {
            _id: '2',
            thumbnail:
              'https://dangkyduhoc.vn/wp-content/uploads/2021/04/52351011-english-british-england-language-education-concept.jpg',
            title: 'English 1',
            des: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to ma",
          },
          {
            _id: '3',
            thumbnail:
              'https://dangkyduhoc.vn/wp-content/uploads/2021/04/52351011-english-british-england-language-education-concept.jpg',
            title: 'English 2',
            des: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to ma",
          },
        ],
      })
    }, 1500)
  },
  methods: {
    showDeck() {
      this.$router.push(`/desks/${this.deckID}`)
    },
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
ul {
  margin: 0;
  padding: 0;
  display: flex;

  li {
    margin: 10px 10px;
    list-style: none;
  }
}
.test-body {
  position: relative;
  background: white;
  padding: 1rem;
  padding-top: 3rem;
}
</style>

