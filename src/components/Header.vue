<template>
<div class="container-fluid">
      <div class = "navbar navbar-default bg-light">
        <div class = "navbar-header">
          <h1 class="navbar-brand">
            <router-link :to = "{name: 'iMain'}">{{ sitename }}</router-link>
          </h1>
        </div>
        <div class = "nav navbar-nav navbar-right cart">
          <router-link
            active-class = "active"
            tag = "button"
            class = "btn btn-default btn-lg"
            :to = "{name: 'Form'}">
          <span
            class = "glyphicon glyphicon-shopping-cart">
{{ cartItemCount }}
     </span> Корзина
          </router-link>
        </div>
      </div>

</div>

</template>

<script>
  export default {
    name: 'my-header',
    data() {
      return {
        sitename: "Матрешкa",
      }
    },
    props: ['cartItemCount'],
    methods: {
      showCheckout() {
        this.$router.push({name: 'Form'});
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  a {
    text-decoration: none;
    color: black;
  }

  .router-link-exact-active {
    color:#2f4f4f;
  }
</style>
