<template>
  <div id="app">


    <div class="col-12 col-lg-6" style="margin-left:auto; margin-right:0;">
      <ul class="nav nav-primary nav-hero">
        <li class="nav-item">
          <a class="nav-link" href="#">TRIPS</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">RECENTLY VIEWED</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">BOOKINGS</a>
        </li>

        <li class="nav-item" style="margin-right: -70px">
          <a class="nav-link" href="#">
            <img class="img-fluid" width="70" height="70" src="./assets/avatar1.jpg" alt="logo">
          </a>
        </li>

      </ul>
    </div>

    <div class="mt-50 contain">
      <router-view/>
    </div>

  </div>
</template>

<script>

    export default {
        name: 'app',


    }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    /*text-align: center;*/
    color: #2c3e50;
    margin-top: 60px;
  }

  @media (min-width: 767px) {

    li a {

      font-size: 17px;
      padding-right: 40px;
      opacity: 1000;
    }

  }

  @media (min-width: 550px){

    .nav-link {
        padding-right: 27px;
    }

    .nav-hero .nav-link{
      font-size: 16px;

    }
  }


  .contain{width:100%;padding-right:80px;padding-left:80px;margin-right:auto;margin-left:auto;}

  @media (max-width: 550px){

    .contain{width:100%;padding-right:20px;padding-left:20px;margin-right:auto;margin-left:auto;}

    nav{

      visibility: visible;

    }


  }
</style>
