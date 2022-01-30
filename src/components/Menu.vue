<template>
  <div class="menu-content">
    <aside class="menu">
      <a class="logo menu__logo" href="#">
        <img
          class="logo__image"
          src="@/assets/img/icons/logo.svg"
          alt="Логотип - Мир говорит"
        />
      </a>
      <Nav/>
      <User />
    </aside>
    <div class="menu-mobile">
      <a class="logo menu-mobile__logo" href="#">
        <img
          class="logo__image"
          src="@/assets/img/icons/logo.svg"
          alt="Логотип - Мир говорит"
        />
      </a>
      <button type="button">
        <img src="@/assets/img/icons/menu-burger.svg" alt="мобильное меню">
      </button>
    </div>
  </div>
</template>

<script>
import User from '@/components/User';
import Nav from '@/components/Nav';

export default {
   name: "Menu",
   components: {
      User,
      Nav
   }
};
</script>

<style lang="scss">
  .menu {
    width: 320px;
    padding-top: 24px;

    position: fixed;
    left: 0;
    top: 0;
    bottom: 0;

    display: flex;
    flex-direction: column;

    overflow: auto;
    background-color: #e5e5e5;

    @media (max-width: 1199px) {
      width: 280px;
    }

    @media (max-width: 991px) {
      width: 250px;
    }

    @media (max-width: 767px) {
      display: none;
    }

    &__logo {
      display: flex;
      justify-content: center;

      margin-bottom: 27px;

      @media (max-widtH: 991px) {
        img {
          max-width: 180px;
        }
      }
    }

    &__nav {
      margin-bottom: 40px;
    }
  }

  .menu-mobile {
    display: none;
    
    padding-top: 8px;
    padding-left: 16px;
    padding-right: 32px;      

    &__logo {
      max-width: 118px;
    }

    @media (max-width: 767px) {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
  }
</style>
