<template>
    <div class="search" id="search">
        <img src="../../assets/logo-peli.jpg" alt="" class="logo">
        <input type="text" class="search__input" placeholder="Hola, busca tu pelicula aquí">
        <div class="login-section">
            <p class="login__title">{{nameUser}}</p>
            <img src="../../assets/download.png" alt="" class="login__img">
            <i class="search__icon arrow"></i>
        </div>
    </div>
</template>

<script>
export default {
  name: '#search',
  data () {
    return {
        nameUser: 'Toni Humanes'
    }
  }
}
</script>

<style lang="scss">
@import './src/scss/search.scss'
</style>
