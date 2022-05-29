<template>
  <li>
    <nuxt-link :to="`/desks/${id}`">
      <div class="card text-white bg-primary">
        <img class="card-img-top" :src="thumbnail" alt="" />
        <div class="card-body">
          <h4 class="card-title">{{ title }}</h4>
          <p class="card-text">{{ des }}</p>
        </div>
      </div>
    </nuxt-link>
  </li>
</template>
<script>

export default{
    props: {
        id: {
            type:Number,
            require:true
        },
        title: {
            type:String,
            require:true,
        },
        des:{
            type:String,
            default:'',
        },
        thumbnail:{
            type:String,
            require:true,
        }
    }
}
</script>
