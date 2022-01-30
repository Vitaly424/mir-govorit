<template>
    <div class="user">
      <a class="user__image" href="#">
        <picture>
          <source srcset="@/assets/img/user.webp" type="image/webp" />
          <img src="@/assets/img/user.png" alt="Пользователь" />
        </picture>
      </a>
      <div class="user__info">
        <a class="user__name" href="#">Екатерина Иванова</a>
        <a class="user__amount" href="#">2 458 ⌘</a>
      </div>
    </div>
</template>

<script>
   export default {
      name: "User"
   }
</script>

<style lang="scss">
  .user {
    margin-top: auto;

    padding-bottom: 16px;
    padding-top: 16px;
    padding-left: 32px;

    display: flex;
    align-items: center;

    box-shadow: 0px -1px 0px rgba(0, 0, 0, 0.25);

    &__image {
      width: 48px;
      height: 48px;
      margin-right: 8px;
    
      border-radius: 8px;
      overflow: hidden;

      img {
        width: 100%;
        height: 100%;

        object-fit: cover;
      }
    }

    &__name {
      display: block;

      font-weight: 700;
      font-size: 14px;
      line-height: 1.4;
      color: #191919;
    }

    &__amount {
      padding: 4px 8px;
      display: inline-block;

      font-weight: 700;
      font-size: 12px;
      line-height: 1;
      letter-spacing: 1px;
      text-transform: uppercase;
      color: #191919;

      background-color: #FACB64;
      border-radius: 8px;
    }
  }
</style>