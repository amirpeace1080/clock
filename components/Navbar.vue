<template>
  <div class="navbar-page">
    <!-- size large -->
    <nav id="navbar" class="nav-container elevation-6 mt-1">
      <ul class="nav">
        <li class="nav-item">
          <a class="nav-link logo" href="#"
            ><img
              src="http://www.elahekarami.ir/NLogo.png"
              alt="logo"
              width="80"
          /></a>
        </li>
        <li class="nav-item">
          <nuxt-link to="/">
            <span class="nav-link">خانه</span>
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link to="/">
            <span class="nav-link">دسته بندی کالاها</span>
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link to="/">
            <span class="nav-link">لوازم آلمانی</span>
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link to="/">
            <span class="nav-link">جعبه موسیقی</span>
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link to="/">
            <span class="nav-link">ساعت مچی</span>
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link to="/">
            <span class="nav-link">ساعت دیواری</span>
          </nuxt-link>
        </li>
      </ul>

      <div id="mobileMenu" class="hambergur-menu" v-b-toggle.sidebar-right>
        <span class="bar"></span>
      </div>
    </nav>
    <!-- end size large -->

    <!-- drop size phone -->
    <b-sidebar id="sidebar-right" right shadow>
      <div class="px-3 py-2 mt-3">
        <div>
        <p>
          <a class="nav-link logo" href="#"
            ><img
              src="http://www.elahekarami.ir/NLogo.png"
              alt="logo"
              width="80"
          /></a>
        </p>
        <p>
          <nuxt-link to="/" class="nav-size-phone">
            <p class="nav-link">خانه</p>
          </nuxt-link>
        </p>
        <p>
          <nuxt-link to="/" class="nav-size-phone">
            <p class="nav-link">دسته بندی کالاها</p>
          </nuxt-link>
        </p>
        <p>
          <nuxt-link to="/" class="nav-size-phone">
            <p class="nav-link">لوازم آلمانی</p>
          </nuxt-link>
        </p>
        <p>
          <nuxt-link to="/" class="nav-size-phone">
            <p class="nav-link">جعبه موسیقی</p>
          </nuxt-link>
        </p>
        <p>
          <nuxt-link to="/" class="nav-size-phone">
            <p class="nav-link">ساعت مچی</p>
          </nuxt-link>
        </p>
        <p>
          <nuxt-link to="/" class="nav-size-phone">
            <p class="nav-link">ساعت دیواری</p>
          </nuxt-link>
        </p>
      </div>
      </div>
    </b-sidebar>
    <!-- end drop size phone -->
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.nav-size-phone{
  text-decoration: none;
  color: black;
}

*,
*:after,
*:before {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  height: 100vh;
}

@mixin flex {
  display: flex;
  justify-content: center;
  align-items: center;
}

.nav-container {
  background-color: #464646;

  .nav {
    list-style: none;
    padding: 0 20px;
    @include flex;
    justify-content: start;

    .nav-item {
      display: inline-block;
      font-size: 18px;
      padding: 0px 10px;
      position: relative;

      .nav-link {
        text-decoration: none;
        display: inline-block;
        color: #fff;
        padding: 5px 10px;
        border: 1px solid rgba(0, 0, 0, 0);
        transition: all 0.2s linear;
        position: relative;
        overflow: hidden;

        &:after {
          background: #fff;
          content: '';
          height: 155px;
          left: -75px;
          opacity: 0.2;
          position: absolute;
          top: -50px;
          transform: rotate(35deg);
          transition: all 550ms cubic-bezier(0.19, 1, 0.22, 1);
          width: 20px;
          z-index: -10;
        } //to make a light reflex

        &:not(.logo):hover {
          border: 1px solid #a5a5a5;
          transform: scale(1.1);
          box-shadow: 0 3px 6px rgba(255, 255, 255, 0.2);

          &:after {
            left: 120%;
            transition: all 550ms cubic-bezier(0.19, 1, 0.22, 1);
          }
        }

        &.logo:hover {
          &:after {
            left: 140%;
            transition: all 550ms cubic-bezier(0.19, 1, 0.22, 1);
          }
        } //logo
      } //nav-link
    } //nav-item
  } //nav

  .hambergur-menu {
    display: none;
    width: 38px;
    height: 33px;
    border: 1px solid #a5a5a5;
    border-radius: 5px;
    float: right;
    margin-right: 20px;

    .bar {
      display: inline-block;
      width: 28px;
      height: 3px;
      background-color: #ccc;
      position: relative;

      &:after,
      &:before {
        content: '';
        position: absolute;
        width: 28px;
        height: 3px;
        background-color: #ccc;
        top: -8px;
        transition: all 0.5s linear;
      }

      &:after {
        top: 8px;
      }
    } //bar
  } //hambegure-menu
} //nav-container

/* The sticky class is added to the navbar with JS when it reaches its scroll position */
.sticky {
  position: fixed;
  top: 0;
  width: 100%;
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.4);
  opacity: 0.9;
}

/* Add some top padding to the page content to prevent sudden quick movement (as the navigation bar gets a new position at the top of the page (position:fixed and top:0) */
.sticky {
  padding-top: 60px;
}

@media only screen and (max-width: 768px) {
  .nav-container {
    height: 50px;
    padding-top: 10px;

    .nav {
      width: 100%;
      height: 100vh;
      overflow-y: hidden;
      background-color: rgba(70, 70, 70, 0.95);
      position: absolute;
      top: -100vh;
      @include flex;
      flex-direction: column;
      transition: all 0.5s linear;

      .nav-item {
        display: block;
      }

      &.open {
        top: 0;
      }
    } //nav

    .hambergur-menu {
      display: block;
      @include flex;
      position: relative;
      z-index: 99999999;

      &.close {
        .bar {
          height: 0;

          &:after {
            top: -2px;
            transform: rotate(135deg);
          }

          &:before {
            top: -2px;
            transform: rotate(45deg);
          }
        }
      }
    } //hambergur-menu
  } //nav-container
} //media


</style>
