<template>
      <nav class="navigation">
    <Logo :title="logoText"/>
      <nuxt-link v-for ="elem in routes" class="link" :to="elem.path" :key="elem.name">{{elem.name}}</nuxt-link>
      <nuxt-link to="/about">About page</nuxt-link>
    <button  class="button" @click="toggleModal('external', $event)">{{text}}</button>
     <Modal v-show="showModal" @modalClose="toggleModal"/>
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
}
},
methods:{
toggleModal(data, event){
  this.showModal =!this.showModal;
}
},
computed: {
  routes(){
    return this.$router.options.routes.filter((elem)=>!elem.path.includes(':'))
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
.link {
  color: black;
}
</style>
