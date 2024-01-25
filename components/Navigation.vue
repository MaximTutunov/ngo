<template>
      <nav class="navigation">
    <Logo/>
      <nuxt-link to="/">Main</nuxt-link>
      <nuxt-link to="/about">About page</nuxt-link>
     <button class="button">{{text}}</button>
     <Modal />
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
  text: "HellRAiser"
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
  color: red;
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
