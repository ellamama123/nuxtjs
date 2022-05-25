<template>
  <div modal="true">
    <div>
      <div :data-modal="name" v-if="visible" class="modal">
        <div
          aria-modal="true"
          data-reach-dialog-content="true"
          tabindex="-1"
          class="modal__mask"
        >
          <div class="modal__body">
            <slot :payload="payload" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VModal from './handle'
export default {
  name: 'ModalLayout',
  props: {
    name: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      payload: null,
      visible: false,
    }
  },
  methods: {
    show(params) {
      console.log('1212')
      this.visible = true
    },
    close(params) {
      this.visible = false
    },
  },
  beforeMount() {
    // open event
    VModal.EventBus.$on('open', (params) => {
      console.log('da vao this' + this.name)
      console.log('da vao param' + params.name)
      if (this.name === params.name) {
        this.show(params)
      }
    })

    VModal.EventBus.$on('close', (params) => {
      if (this.name === params.name) {
        this.close(params)
      }
    })
  },
}
</script>

<style lang="scss">
.modal {
  display: flex;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0, 0, 0, 0.575);
  align-content: center;
  justify-content: space-around;
  align-items: center;

  &__body {
    background: white;
  }
}
</style>