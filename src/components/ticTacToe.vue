<template>
  <div class="row container"  >
    <div class="col-12">
      <nav class="navbar navbar-light bg-light">
        <span class="navbar-brand mb-0 h1">TIC TAC TOE</span>
      </nav>
      <div class="row p-5" id = "game" >
        <div class="col-6 ml-5">
          <div class="" v-show="gameStarted == true">
            <div class="row">
            <div class="col">
                <button @click="clicked(1 , 0,0)" value = 1 id = 1> 1 </button>
                <button @click="clicked(2 , 0,1)" id = 2>1</button>
                <button @click="clicked(3 , 0,2)" id = 3>1</button>
            </div>
          </div>

          <div class="row">
            <div class="col">
                <button @click="clicked(4 , 1,0)" id = 4>1</button>
                <button @click="clicked(5 , 1,1)" id = 5>1</button>
                <button @click="clicked(6 , 1,2)" id = 6>1</button>
            </div>
          </div>

          <div class="row">
            <div class="col">
                <button @click="clicked(7 , 2,0)" id = 7>1</button>
                <button @click="clicked(8 , 2,1)" id = 8>1</button>
                <button @click="clicked(9 , 2,2)" id = 9>1</button>
            </div>
          </div>
          </div>
        </div>
        <div class="col-3" v-show="gameStarted == false">
          {{errorMessage}}
            <div class="form-group">
                <input type="text" v-model="player.x_player" placeholder="x-player name" class="form-control" :disabled="gameStarted" >
              </div>
            <div class="form-group">
              <input type="text" class="form-control" v-model="player.o_player" placeholder="o-palyer name" :disabled="gameStarted" >
            </div>
            <button id="startGame-Button" @click="startGame() ">Start</button>
            
        </div>
        <div class="col-5" v-show="gameStarted == true">
            <h1>{{ gameStatus }}</h1>
            <p>{{chance}}</p>
            <button id="resetGame-Button"   @click="resetGame() ">Re-set</button>
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
        gameStarted:false,
        errorMessage : null,
        gameReset:true,
        chance : null,
        player:{
          x_player : null,
          o_player : null
        },
        gameStatus :"Match In Progress",
        inputMetrix:[
            [1,2,3],
            [4,5,6],
            [7,8,9]
          ],
        
      }
    },
    computed: {
      
    },
    methods:{
      winCheck(){
        if(this.inputMetrix[0][0] == this.inputMetrix[0][1] && this.inputMetrix[0][0] == this.inputMetrix[0][2]){


          document.getElementById("resetGame-Button").innerHTML = "Play Again : )"
          alert()
        }else if(this.inputMetrix[1][0] == this.inputMetrix[1][1] && this.inputMetrix[1][0] == this.inputMetrix[1][2]){

          document.getElementById("resetGame-Button").innerHTML = "Play Again : )"
          alert()
        }else if(this.inputMetrix[2][0] == this.inputMetrix[2][1] && this.inputMetrix[2][0] == this.inputMetrix[2][2]){

          document.getElementById("resetGame-Button").innerHTML = "Play Again : )"
          alert()
        }else if(this.inputMetrix[0][0] == this.inputMetrix[1][0] && this.inputMetrix[1][0] == this.inputMetrix[2][0]){

          document.getElementById("resetGame-Button").innerHTML = "Play Again : )"
          alert()
        }else if(this.inputMetrix[0][1] == this.inputMetrix[1][1] && this.inputMetrix[1][1] == this.inputMetrix[2][1]){

          document.getElementById("resetGame-Button").innerHTML = "Play Again : )"
          alert()
        }else if(this.inputMetrix[0][2] == this.inputMetrix[1][2] && this.inputMetrix[1][2] == this.inputMetrix[2][2]){

          document.getElementById("resetGame-Button").innerHTML = "Play Again : )"
          alert()
        }else if(this.inputMetrix[0][0] == this.inputMetrix[1][1] && this.inputMetrix[1][1] == this.inputMetrix[2][2]){

          document.getElementById("resetGame-Button").innerHTML = "Play Again : )"
          alert()
        }else if(this.inputMetrix[0][2] == this.inputMetrix[1][1] && this.inputMetrix[1][1] == this.inputMetrix[0][2]){

          document.getElementById("resetGame-Button").innerHTML = "Play Again : )"
          alert()
        }
      },

      startGame(){
        if(this.player.x_player.length > 0 && this.player.o_player.length > 0 ){
          this.errorMessage = null
          this.gameStarted = true
          this.chance = this.player.x_player
        }else{
          this.errorMessage = "please enter player names first"
        }
        

      },

      resetGame(){

        this.gameReset =false
        this.gameStarted = false

        // reset all the thing 
        location.reload(true)

      },

      clicked(e ,x,y){
        this.count ++;
        document.getElementById(e).disabled = true
        if (this.count % 2 ){

          // chance changed to -> O player
          this.chance = this.player.o_player

          document.getElementById(e).innerHTML = "X" 
          this.inputMetrix[x][y] = "X"
          this.winCheck()
          
        } else{

          // chance changed to -> X player
          this.chance = this.player.x_player

          document.getElementById(e).innerHTML = "O" 
          this.inputMetrix[x][y] = "O"
          this.winCheck()
        }
        
      }
    }
}
</script>


<style scoped>
  button{
    background-color: rgba(255, 251, 0, 0.959);
    padding: 35px;
    padding-left:50px;
    padding-right: 50px;
    border: 3px solid rgba(148, 118, 64, 0.753);
    font-size: 1.5em;
    transition-duration: 0.4s;
  }

  #startGame-Button{
    background-color: rgb(42, 10, 184); /* Green */
    border: none;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px; 
    margin-right: 2px;
  }

  #resetGame-Button{
    background-color: rgb(194, 11, 148); /* Green */
    border: none;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
  }

button:hover {
  background-color: rgb(243, 142, 26); /* Green */
  color: white;
}

  #game{
    background-color: rgb(191, 243, 252)
  }
</style>
