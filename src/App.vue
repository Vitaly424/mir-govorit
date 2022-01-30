<template>
  <div class="info">
    <Menu />
    <Content :data = "data"/>
  </div>
</template>

<script>
import Menu from "@/components/Menu";
import Content from "@/components/Content";

export default {
  name: "App",
  components: {
    Menu,
    Content
  },
  data() {
    return {
      queryString: "",
      data: null,
    };
  },
  methods: {
    async getCards() {
      this.queryString = "https://eg-cdn.s3.eu-central-1.amazonaws.com/static/fe-test/seminars-test-data.json";
      const response = await fetch(this.queryString);
      const data = await response.json();
      this.data = data;
    },
  },
  mounted() {
    this.getCards();
  },
};
</script>

<style lang="scss">
  @import "@/assets/scss/main.scss";
  
  .button {
    padding: 8px 16px;

    margin-top: auto;
    margin-left: auto;
    
    background-color: #007FF4;
    border-radius: 8px;

    font-weight: 700;
    font-size: 14px;
    line-height: 1.4;
    color: #ffffff;

    transition: background-color 0.2s linear;
    
    @include hover {
      background-color: darken(#007FF4, 10%);
    }

    &--seminar {
      background-color: #FBAD00;
      pointer-events: none;
    }
  }

  .info {
    min-height: 100vh;
  }
</style>
