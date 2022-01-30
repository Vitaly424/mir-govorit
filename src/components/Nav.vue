<template>
    <nav class="nav menu__nav">
      <ul class="nav__list">
        <li class="nav__item">
          <a class="nav__link" href="#">
            Мой кабинет
            <img src="@/assets/img/icons/arrow.svg" alt="" />
          </a>
        </li>

        <li class="nav__item">
          <a class="nav__link nav__link--active" href="#">
            Обучение
            <img src="@/assets/img/icons/arrow.svg" alt="" />
          </a>
          <ul class="submenu nav__submenu">
            <li class="submenu__item">
              <a class="submenu__link submenu__link--active" href="#"
                >Семинары и&nbsp;курсы</a
              >
            </li>

            <li class="submenu__item">
              <a class="submenu__link" href="#">Вебинары</a>
            </li>

            <li class="submenu__item">
              <a class="submenu__link" href="#">Самообучение</a>
            </li>

            <li class="submenu__item">
              <a class="submenu__link" href="#">Тьютор</a>
            </li>
          </ul>
        </li>

        <li class="nav__item">
          <a class="nav__link" href="#"> Чат </a>
        </li>

        <li class="nav__item">
          <a class="nav__link" href="#"> Конкурсы </a>
        </li>
      </ul>
    </nav>
</template>

<script>
   export default {
      name: "Nav"
   }
</script>

<style lang="scss">
  @import "@/assets/scss/base/mixins.scss";

  .nav {
    &__item {
      &:not(:last-child) {
        margin-bottom: 8px;
      }
    }

    &__link {
      position: relative;
      display: block;

      padding-top: 3.5px;
      padding-bottom: 3.5px;
      padding-left: 32px;
      padding-right: 64px;

      font-weight: 700;
      font-size: 16px;
      line-height: 1.5;
      color: #191919;

      transition: background-color 0.2s linear;

      img {
        position: absolute;
        right: 40px;
        top: 50%;

        transform: translateY(-50%);
      }

      &--active {
        img {
          top: 12%;
          transform: rotate(90deg);
        }
      }

      @include hover {
        background-color: #FACB64;
      }
    }
  }
  
  .submenu {
    &__link {
      display: block;
      padding-left: 54px;
      padding-right: 30px;
      padding-top: 3px;
      padding-bottom: 3px;
      
      font-weight: 400;
      font-size: 16px;
      line-height: 1.5;
      color: #191919;

      transition: background-color 0.2s linear;

      @include hover {
        background-color: #FACB64;
      }

      &--active {
        background-color: #FACB64;
      }
    }
  }
</style>