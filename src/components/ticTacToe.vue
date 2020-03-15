<template>
  <div class="row container" >
    <div class="col-6 border ml-5">
      <div class="row">
        <div class="col">
            <button @click="clicked(1)" value = 1 id = 1></button>
        </div>
        <div class="col">
            <button @click="clicked(2)" id = 2>1</button>
        </div>
        <div class="col">
            <button @click="clicked(3)" id = 3>1</button>
        </div>
      </div>

      <div class="row">
        <div class="col">
            <button @click="clicked(4)" id = 4>1</button>
        </div>
        <div class="col">
            <button @click="clicked(5)" id = 5>1</button>
        </div>
        <div class="col">
            <button @click="clicked(6)" id = 6>1</button>
        </div>
      </div>

      <div class="row">
        <div class="col">
            <button @click="clicked(7)" id = 7>1</button>
        </div>
        <div class="col">
            <button @click="clicked(8)" id = 8>1</button>
        </div>
        <div class="col">
            <button @click="clicked(9)" id = 9>1</button>
        </div>
      </div>

    </div>

  </div>
</template>

<script>
export default {
  name: 'TicTacToe',
  
  data(){
      return{
        count : 0,
        player:{
          One : 'Dilshan',
          Two : 'Gayathri'
        }
      }
    },
    computed: {
       
    },
    methods:{
      matricks(){
        []
      },
      clicked(e){
        this.count ++;

        document.getElementById(e).disabled = true
        if(this.count % 2 ){
          document.getElementById(e).innerHTML = "X" 
        } else{
          document.getElementById(e).innerHTML = "O" 
        }
        
      }
    }
}
</script>


<style scoped>

</style>
