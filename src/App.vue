<template>
    <login></login>
   
    <!-- <div class="toasts"> -->
        <TransitionGroup name="slide-left" tag="div" class="toasts">
        <the-toast v-for="(toast, i) in toasts" :key="i" :message="toast.message" :toastType="toast.type"></the-toast>
        </TransitionGroup>
    <!-- </div> -->
</template>

<script>

import Login from "./components/Login.vue"
import TheToast from "./components/TheToast.vue"
export default{
    data:()=>({
      toasts:[
        // {
        //     type:"success",
        //     message:"Done Success"
        // },
        // {
        //     type:"Error",
        //     message:"Error Here"
        // }
      ],
      
    }),
   mounted(){
    this.$eventBus.on('errorToast',data=>{
         this.toasts.push(data);
         this.removeOneToast();
    })

   }, 
   methods:{
      removeOneToast(){
        setTimeout(()=>{
          this.toasts.shift();
        },2222)
      }
   },
  components:{
      Login,
      TheToast
}
}


</script>
<style scoped>
.slide-left-enter-active,
.slide-left-leave-active {
  transition: all 0.5s ease;
}
.slide-left-enter-from,
.slide-left-leave-to {
  opacity: 0;
  transform: translateX(30px);
}
</style>
