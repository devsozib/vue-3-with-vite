<template>
  <div style="text-align: center;">
     <header>
  <h2>{{ msg }}</h2>  
  </header>
   <div class="container" key="">
       <h5>Credit card info</h5>
       <card-component 
       v-model:nameOnCard="nameOnCard"
       v-model:cardNumber="cardNumber"
       v-model:expiry="expiry"
       ></card-component>
       <br/>
       <br/>
       <br/>
       <br/>
       <br/>

       <p>
        name: {{ nameOnCard }}<br/>
        CardNumber: {{ cardNumber }} <br/>
        Expiry: {{ expiry }} <br/>
       </p>
   </div>
  </div>

</template>

<script>
import CardComponent from './components/CardComponent.vue';

export default{
   data(){
       return{
        msg:"Vue with vite",
        nameOnCard:"",
        cardNumber:"",
        expiry:""
       }
   }, 
   methods:{},
   components:{
     CardComponent
   }
}
</script>
<style scoped>
body {
  font-family: sans-serif;
  line-height: 1.8;
}
header {
  background-color: #1f2c46;
  color: #41b883;
  font-size: 22px;
  padding: 22px;
}
</style>
