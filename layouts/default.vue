<template>
    <div>
        <default-header />
        <nuxt />
        <footer-default />
    </div>
</template> 

<script>
import FooterDefault from '../components/Footer/FooterDefault.vue'
import DefaultHeader from '../components/Header/DefaultHeader.vue'
export default {
  components: { DefaultHeader, FooterDefault },
  name: 'DefaultPage',
}
</script>