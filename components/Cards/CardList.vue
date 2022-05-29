<template>
  <div class="col-md-4">
    <div class="flip-card mt-2">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img
            :src="thumbnail"
            alt="Avatar"
            style="width: 300px; height: 300px"
          />
        </div>
        <div class="flip-card-back" style="width: 300px; height: 300px">
          <h1>{{ title }}</h1>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      require: true,
    },
    thumbnail: {
      type: String,
      require: true,
    },
  },
}
</script>
