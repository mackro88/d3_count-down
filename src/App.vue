<template>
  <div id="app">
    <h3>Inicia la cuenta regresiva en...</h3>
    <button @click="setCountdown(4)">4 segs</button>
    <button @click="setCountdown(10)">10 segs</button>
    <button @click="setCountdown(24)">24 segs</button>
    <div id="showCountdown">---> {{countDown}} segundos</div>
  </div>
</template>

<script>
export default {
  name: "App",
  data: ()=>{
    return{
      countDown: 0,
      active: false
    }
  },
  methods: {
    setCountdown(value){
      
      this.countDown = value
      if (this.active == true ) { //Intentando detener el countdown al apretar un botón si este ya ha iniciado, pero no funciona
        clearInterval(time)
      }
      let time = setInterval(() => {
          this.active == true
          this.countDown--
          if (this.countDown==0) {
            clearInterval(time);
            this.active == false
          }
      }, 1000);
    }
  } 
};
</script>

<style scoped lang="scss">
  #showCountdown{
    margin: 10px;
  }
  button{
    display: inline-block;
    margin-right: 5px;
  }
</style>
