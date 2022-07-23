<template>
  <div>
     <label for="">Name</label>
     <input type="text" :value="nameOnCard" @input="handleInput('update:nameOnCard', $event)"><br/>
      <label for="">Cardnumber</label>
     <input type="text" :value="cardNumber" @input="handleInput('update:cardNumber', $event)"><br/>
      <label for="">EXpiry</label>
     <input type="text" :value="expiry" @input="handleInput('update:expiry', $event)"><br/>
  </div>
</template>

<script>
export default {

    props:{
        nameOnCard:{
            type: String,
            default:""
        },
          cardNumber:{
            type: String,
            default:""
        },
          expiry:{
            type: String,
            default:""
        },
    },
    methods:{
        handleInput(eventName, e){
            this.$emit(eventName, e.target.value);
        }
    }

}
</script>

<style scoped>
.contact-details {
  border: 1px solid gray;
  margin: 11px 22px;
  padding: 22px;
}
.contact-heading {
  color: rgb(0, 73, 107);
}
</style>
Footer
© 2022 GitHub, Inc.