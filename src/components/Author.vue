<template>
   <div class="author content__author">
      <div class="author__box">
         <div class="author__content">
            <p class="author__text">{{author.topic}}</p>
            <h2 class="author__name">{{author.name}}</h2>
            <p class="author__description">
               {{author.description}}
            </p>
         </div>
         <a class="author__image" href="#">
            <img :src="author.avatar" alt="Наставник">     
         </a>
      </div>
       <p class="author__description author__description--mobile">
         {{author.description}}
       </p>
   </div>
</template>

<script>
   export default {
      name: "Author",
      props: {
         author: {
            type: Object,
            require: true
         }
      }
   }
</script>

<style lang="scss">
   @import "@/assets/scss/base/mixins.scss";

  .author {
    max-width: 601px;
   
    &__box {
       display: flex;
       align-items: center;
    }

    &__content {
       margin-right: 16px;

       @media (max-width: 575px) {
          margin-right: 0;
       }
    }

    &__text {
      font-weight: 700;
      font-size: 12px;
      line-height: 1.3;
      letter-spacing: 1px;
      text-transform: uppercase;
      color: #191919;
    }

    &__name {
      margin-bottom: 8px;

      font-weight: 700;
      font-size: 24px;
      line-height: 1.3;
      color: #191919;
    }

    &__description {
      font-size: 16px;
      line-height: 24px;
      color: #000000;

      @media (max-width: 991px) {
         display: none;
      }

      &--mobile {
         display: none;
         margin-top: 8px;

         @media (max-width: 991px) {
            display: block;
         }
      }
    }

    &__image {
      width: 120px;
      height: 120px;

      border-radius: 50%;
      overflow: hidden;
      flex-shrink: 0;

      transition: box-shadow 0.2s linear;
      @include hover {
        box-shadow: 0 0 12px 2px #000000;
      }

      img {
        display: block;

        width: 100%;
        height: 100%;
        
        object-fit: cover;
      }
    }
  }
</style>