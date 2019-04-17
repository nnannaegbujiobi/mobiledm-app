<template>

  <div id="app" >
  <div class="animal">
    <div id="box">
      <h1>Tamagotchi 3000</h1>
         <h3>Hours alive:{{timer}}</h3>
        <p> {{moods[life]}}</p>
  
    <button v-on:click="addTime"> Wait One Hour </button> <br>
    <button v-on:click="addPet">Pet</button>
  </div>
  </div>
</div>
</template>

<script>

export default {
  data()  {
    return {
      timer: 0, 
      life: 4,
      moods: ['😧','🙁','😐','🙂','😍'],
      pet: 0
    };
  },
   
  methods: {
    addTime() {
      var timePast = this.timer;
      this.timer += 1 ;
      if (this.life >= 1) {
        if (timePast < this.timer && this.pet === 0) {
          this.life -= 1;
        } else if (timePast < this.timer && this.pet > 1) {
          this.life += 1;
        }
      }
      this.pet = 0;
    }, 
      
    addPet() {
      this.pet += 1;

    }

  },
    


};


</script>


<style scoped>


  #box {
    background-color: ##ffffff;
    padding: 250px;
    margin: 20px;
    margin-bottom: 50px;
    outline: solid black;
    height: 30
  }

  img {
    margin-top: 50px;
    margin-right: 50px;
  }
  
  p {
    font-size: 10em;
  }
    

</style>