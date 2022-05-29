<template>
  <div>
    <div class="container">
      <h3>Deck {{ $route.params.id }}: Learning {{ deck.title }}</h3>
      <div class="tools">
        <div class="btn btn-success">Start now</div>
        <div class="btn btn-primary" @click.prevent="openModal">
          Creat a card
        </div>
      </div>
      <div class="desk-list" style="height: 700px">
        <div class="row">
          <card-list
            v-for="card in cards"
            :key="card._id"
            :thumbnail="card.thumbnail"
            :title="card.title"
          />
        </div>
      </div>
      <v-modal name="CreatCardModal">
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
  </div>
</template>

<script>
import CardList from '@/components/Cards/CardList.vue'
export default {
  components: { CardList },
  name: 'DeckInfo',
  validate(context) {
    console.log(context)
    return /^[0-9]$/.test(context.params.id)
  },
  data() {
    return {
      cards: [
        {
          _id: '1',
          thumbnail:
            'https://cdn.tgdd.vn/Files/2019/10/24/1211885/duong-tinh-luyen-la-gi-co-nen-su-dung-duong-tinh-luyen-hay-khong-201910241522445701.jpg',
          title: 'Sugar',
          des: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to ma",
        },
        {
          _id: '2',
          thumbnail:
            'https://baokhanhhoa.vn/dataimages/201909/original/images5377069_hoa.jpg',
          title: 'Flower',
          des: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to ma",
        },
        {
          _id: '3',
          thumbnail:
            'https://maivangthuduc.com/wp-content/uploads/2017/12/20-C%C3%82Y-XANH.jpg',
          title: 'Tree',
          des: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to ma",
        },
      ],
    }
  },
  asyncData(context, callback) {
    console.log('hello')
    // eslint-disable-next-line
    setTimeout(() => {
      callback(null, {
        deck: {
          _id: '1',
          thumbnail:
            'https://dangkyduhoc.vn/wp-content/uploads/2021/04/52351011-english-british-england-language-education-concept.jpg',
          title: `English ${context.params.id}`,
          des: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to ma",
        },
      })
    }, 1500)
  },
  methods: {
    openModal() {
      console.log('12121')
      this.$modal.open({ name: 'CreatCardModal' })
    },
    closeModal() {
      console.log('12121')
      this.$modal.close({ name: 'CreatCardModal' })
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
// button.btn.btn-danger {
//   position: absolute;
//   top: 0;
//   right: 0;
// }
</style>

