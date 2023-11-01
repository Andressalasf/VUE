<script setup>
import { ref } from 'vue';


let notifications = ref(0)

function addValue() {
  notifications.value++
  console.log(notifications)
}

function minusValue(){
  if(notifications.value >=1){
    notifications.value--
  }
}
addValue();




</script>

<template>
  <div class="wrapper">
    <div class="profile">
       
      <div class="notification" v-show="notifications > 0" >{{ notifications }}</div>
    </div>
    <div class="button-wrapper">
      <div class="button" @click="minusValue">-</div>
      <div class="button" @click="addValue">+</div>
    </div>
    <div>
      <div v-if="notifications == 0">
        Buu!!! nadie te escribe 👉👌
      </div>
      <div v-else>
        Revisa tu inbox 🚯🚯🚳
      </div>
  </div>
  </div>
  
</template>

<style scoped>
.wrapper{
  background-color: #348888;
  width: 60% ;
  border-radius: 12px;
  margin: 0 auto;
  padding-top: 32px;
  overflow: hidden;
}
.profile{
  background-color: purple;
  width: 120px;
  height: 120px;
  border-radius: 100%;
  margin: 0 auto;
  position: relative;
  background-image: url('data:image/jpeg;base64,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');
  background-size: cover;
}
.notification{
  position: absolute;
 background-color: red;
 min-width: 18px;
 height: 18px;
 border-radius: 100%;
 display: flex;
 align-items: center;
 justify-content: center;
 color: white;
 top: 0;
 right: 0;

}
.button-wrapper{
  text-align: center;
  margin-top: 12px;
  padding-bottom: 16px;



}
.button{
  background-color: #fa7f08;
  border-radius: 4px;
  padding: 2px 0;
  font-weight: bold;
  color: white;
  width: 40px;
  display: inline-block;
  cursor: pointer;
  
}

.button:first-child{
  margin-right: 8px;
}

.button:last-child{
  margin-left: 8px;
}


</style>
