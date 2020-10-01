<template>
  <div id="app">
    <b-container class="bv-example-row d-flex flex-column align-items-center">
      <h1>{{mainMessage}}</h1>
      <b-row class="w-50 mb-1">
        <b-col class="p-0 d-flex align-items-center  ">
          <b-form-input class="text-center"
            v-model="price"
            placeholder="Original Price"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="w-50 mb-1">
        <b-col class="p-0 text-center d-flex align-items-center">
          <b-form-input class="text-center"
            v-model="discountPrice"
            placeholder="What type of discount?"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="w-50 mb-1">
        <b-button variant="primary" class="w-100" @click="displayYourePay">
          CALCULATE
        </b-button>
      </b-row>
      <b-row class="w-50 mb-1">
        <b-button variant="danger" class="w-100" @click="displayPercentDiscount">
          CALL : YOU'RE SAVING
        </b-button>
      </b-row>
  <!--    <b-row class="w-50 text-left mb-1 bg-primary p-2 text-white">
        <b-col class="p-0">
          <div><span>DISCOUNT% : </span></div>
        </b-col>
        <b-col class="p-0">
          <span>{{ result }} $ : </span>
        </b-col>
    </b-row>   !-->

      <b-row class="w-50 mb-1 bg-secondary text-white">
        <b-col class="p-2">
          You're Pay : {{result}} $
        </b-col>
      </b-row>
      <b-row class="w-50 mb-1 bg-secondary text-white">
        <b-col class="p-2">
          You're Saving : {{discount}}  $
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  name: "App",
  data: function () {
    return {
      price: null,
      discountPrice: null,
      result: null,
      mainMessage:'DISCOUNT CALCULATOR',
      discount:0,
    };
  },
  methods: {
    displayYourePay: function () {
      return (this.result = this.price - (this.price * this.discountPrice) / 100);
    },
    displayPercentDiscount:function(){
      return this.discount=this.result-this.price;
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
