<template>
  <main class="content">
    <Header />
    <Author :author = "data.author"/>

    <div class="content__list">
      <Card
        v-for="card in getFilterData"
        :key="card.id"
        :name="card.title"
        :type="card.type"
        :duration="card.duration"
        :price="card.price"
        :date-start = "card.dateStart" 
        :description = "card.description"
        :curators = "card.curators"
        :methodists = "card.methodists"
      />
    </div>
  </main>
</template>

<script>
import Header from "@/components/Header";
import Author from "@/components/Author";
import Card from "@/components/Card";

export default {
  name: "Content",
  props: {
    data: {
      type: Object,
      require: true
    }
  },
  components: {
    Header,
    Author,
    Card
  },
  computed: {
   getFilterData() {
      let seminar = this.data.seminars.filter(obj => obj.type === 'seminar');
      let training = this.data.seminars.filter(obj => obj.type === 'training');

      return [...seminar, ...training];
   }
  },
};
</script>

<style lang="scss">
   .content {
      padding: 32px;
      padding-left: 353px;
      padding-right: 64px;

      @media (max-width: 1199px) {
         padding-left: 303px;
         padding-right: 30px;
      }

      @media (max-width: 991px) {
         padding-left: 270px;
      }

      @media (max-width: 767px) {
         padding-left: 16px;
         padding-right: 16px;
      }
   
      &__list {
         max-width: 1183px;

         display: grid;
         grid-template-columns: repeat(auto-fill, 224px);
         grid-column-gap: 16px;
         grid-row-gap: 24px;

         @media (max-width: 640px) {
            grid-template-columns: repeat(2, 1fr);
         }

         @media (max-width: 575px) {
            grid-template-columns: 1fr;
         }
      }

      &__header {
         margin-bottom: 32px;
      }

      &__author {
         margin-bottom: 24px;
      }
   }
</style>
