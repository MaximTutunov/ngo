<template>
      <nav class="navigation">
    <Logo :title="logoText"/>
      <nuxt-link v-for ="elem in linksArray" class="link" :to="elem.to" :key="elem.title">{{elem.title}}</nuxt-link>
      <nuxt-link to="/about">About page</nuxt-link>
    <button  class="button" @click="counter+=1">{{text}}</button>
    <p>{{ counter }}</p>
    <input type="checkbox" v-model="showModal"/>
     <Modal v-show="showModal"/>
    </nav>

</template>

<script>
import Logo from './navigation/Logo';
export default {
components:{
  Logo
},
data(){
  return{
  text: "Enter",
  logoText: "NKO Project",
 linksArray: [
  {to:'/', title:'Main'},
  {to:'/about', title:'about page'},
 ],
 showModal: false,
 counter: 0,
}
}
  }
</script>

<style  scoped>

.navigation {
  width: 100%;
  height: 80px;
  padding: 20px;
  position: fixed;
  color: rgb(60, 0, 255);
  top: 0;
  left: 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: lightblue;
}
.button{
  width: 100px;
  padding: 10px 15px;
  background: white;
  color: black;
  border: 1px solid black;
  border-radius: 30px;
  cursor: pointer;
  transition: .3s;
}
.button:hover{
  background: black;
  color: white;
  transition: .3s;
}
</style>
