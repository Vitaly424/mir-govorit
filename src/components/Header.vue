<template>
    <header class="header content__header">
        <h1 class="header__title">Витрина <span>Семинары и курсы</span></h1>
        <a class="header__training" href="#">Моё обучение</a>
   </header>
</template>

<script>
   export default {
      name: "Header"
   }
</script>

<style lang="scss">
   @import "@/assets/scss/base/mixins.scss";

  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;

    &__title {
      font-weight: 700;
      font-size: 36px;
      line-height: 1.3;
      color: #191919;

      @media (max-width: 1199px) {
        display: flex;
        flex-direction: column;
      }
      
      @media (max-width: 991px) {
        font-size: 24px;
      }

      span {
        font-weight: 700;
        line-height: 1.3;
        color: #C4C4C4;
        margin-left: 10px;

        @media (max-width: 1199px) {
          margin-left: 0;
          margin-top: 8px;
        }

        @media (max-width: 575px) {
          font-size: 16px;
        }
      }
    }

    &__training {
      padding: 11px;

      font-weight: 700;
      font-size: 16px;
      line-height: 1.5;
      color: #007FF4;

      transition: color 0.2s linear;  

      @media (max-width: 575px) {
        padding: 0;
      }

      @include hover {
        color: darken(#007FF4, 7%);
      }
    }
  }
</style>