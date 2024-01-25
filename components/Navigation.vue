<template>
      <nav class="navigation">
    <Logo :title="logoText"/>
      <nuxt-link to="/">Main</nuxt-link>
      <nuxt-link to="/about">About page</nuxt-link>
     <button v-if="showBtn1" class="button">{{text}}</button>
     <button v-else-if="showBtn2" class="button">test 1</button>
     <button v-else class="button">test 2</button>
     <Modal v-if="false"/>
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
  showBtn1: false,
  showBtn2: false,


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
