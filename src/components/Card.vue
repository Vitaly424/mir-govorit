<template>
  <div class="card">
    <div class="card__content">
      <h3 class="card__name">{{name}}</h3>

      <ul class="card__list">
        <li class="card__item">
          <img :src="require(`@/assets/img/icons/type-${getImage}.svg`)" alt="">
          <span>{{type}}</span>
        </li>

        <li class="card__item" v-if="isDuration">
          <img src="@/assets/img/icons/duration.svg" alt="">
          <span>{{duration}} месяцев</span>
        </li>

        <li class="card__item" v-if="isDataStart">
          <img src="@/assets/img/icons/start.svg" alt="">
          <span>{{dateStart}}</span>
        </li>
      </ul>

      <div class="card__info" v-if="isDescription">
        <p class="card__text">
          {{description}}
        </p>
      </div>

      <ul class="card__mentors">
        <li class="card__mentor" v-if="isCurators">
            Куратор:
            <span>
              {{getCurators}}
            </span>
        </li>

        <li class="card__mentor" v-if="isMethodists">
            Методисты:
            <span>
              {{getMethodists}}
            </span>
        </li>
      </ul>
    </div>

    <button type="button" :class="classObject" :disabled="isButtonDisabled">{{getContentButton}}</button>
  </div>
</template>

<script>
export default {
   name: 'Card',
   props: {
      name: {
         type: String,
         require: true
      },
      type: {
         type: String,
         require: true
      },
      duration: {
         type: Number
      },
      price: {
        type: Number
      },
      dateStart: {
        type: String
      },
      description: {
        type: String
      },
      curators: {
        type: Array
      },
      methodists: {
        type: Array
      }
  },
  data() {
    return {
    }
  },
  computed: {
    classObject() {
      return {
        'button': true,
        'button--seminar': this.type === 'seminar'
      }
    },
    getContentButton() {
      return this.type === 'seminar' ? this.price + " ₽" : "Выбрать тариф";
    },
    getImage() {
      return this.type === 'seminar' ? "seminar" : "training" ;
    },
    getCurators() {
      return this.curators.join(', ');
    },
    getMethodists() {
      return this.methodists.join(', ');
    },
    isButtonDisabled() {
      return this.type === 'seminar' ? true : false;
    },
    isDataStart() {
      return this.dateStart === undefined ? false : true 
    },
    isDescription() {
      return this.description === "" ? false : true 
    },
    isDuration() {
      return this.duration === undefined ? false : true 
    },
    isCurators() {
      return this.curators === undefined ? false : true 
    },
    isMethodists() {
      return this.methodists === undefined ? false : true 
    } 
  }
};
</script>

<style lang="scss">
  .card {
      display: flex;
      flex-direction: column;

      padding: 16px;
      padding-top: 20px;

      min-height: 320px;
      width: 224px;

      background-color: #ffffff;
      border: thin solid #EDEDED;
      box-shadow: 0px 6px 8px rgba(0, 0, 0, 0.03);
      border-radius: 8px;

      @media (max-width: 640px) {
        width: 100%;
      }

      &__name {
        margin-bottom: 4px;

        font-weight: 700;
        font-size: 18px;
        line-height: 1.3;
        color: #191919;
      }

      &__list {
        margin-bottom: 10px;
      }

      &__content {
        margin-bottom: 28px;
      }

      &__item {
        display: flex;
        align-items: flex-start;

        font-weight: 500;
        font-size: 14px;
        line-height: 1.4;
        color: #191919;

        img {
          margin-right: 10px;
        }

        &:not(:last-child) {
          margin-bottom: 4px;
        }
      }

      &__info {
        margin-bottom: 8px;
      }

      &__text {
        font-size: 12px;
        line-height: 1.3;
        color: #191919;
      }

      &__mentor {
        font-size: 12px;
        line-height: 1.3;
        color: #191919;
      }
  }
</style>
