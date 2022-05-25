<template>
    <nav>
      <ul>
        <li>
          <nuxt-link to="/">
            Home
          </nuxt-link>
        </li>
        <li>
           <nuxt-link to="/desks">Desk</nuxt-link>
          </li>
        <li>
           <nuxt-link to="/profile">Profile</nuxt-link>
        </li>
        <li>
           <nuxt-link to="/settings">Settings</nuxt-link>
        </li>
      </ul>
    </nav>
</template>

<script>
export default {
    name:'DefaultHeader'
}
</script>

<style lang="scss" scoped>
nav {
  background: #9a9aff;
    padding: 20px 0px;
    ul {
      width: 80%;
      margin:0 auto;
      li {
        a {
          text-decoration: none;
          font-size: 20px;
          font-weight: bold;
          &.nuxt-link-exact-active {
            color: aqua;
          }
        }
      }
    }
}
</style>
