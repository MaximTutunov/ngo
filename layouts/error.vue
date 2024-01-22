<template>
  <div class ='error-block'>
<h1>У нас ошибка!!</h1>
<h2>Status {{ error.statusCode }}</h2>
<h2>message {{ error.message }}</h2>
  </div>
</template>

<script>
  export default {
props:{
  error:{
    type: Object,
    default:()=> ({})
  }
},
mounted(){
  console.log(this.error, "ERROR OBJECT")
}
  }
</script>

<style  scoped>
.error-block {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  height: 100vh;
}
</style>
