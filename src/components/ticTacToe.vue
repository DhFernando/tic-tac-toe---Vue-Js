<template>
  <div class="row container" >
    <div class="col-6 border ml-5">
      <div class="row">
        <div class="col">
            <button @click="clicked(1 , 0 , 0)" value = 1 id = 1></button>
        </div>
        <div class="col">
            <button @click="clicked(2 , 0,1)" id = 2>1</button>
        </div>
        <div class="col">
            <button @click="clicked(3 ,0,2)" id = 3>1</button>
        </div>
      </div>

      <div class="row">
        <div class="col">
            <button @click="clicked(4 ,1,0)" id = 4>1</button>
        </div>
        <div class="col">
            <button @click="clicked(5 ,1,1)" id = 5>1</button>
        </div>
        <div class="col">
            <button @click="clicked(6 ,1,2)" id = 6>1</button>
        </div>
      </div>

      <div class="row">
        <div class="col">
            <button @click="clicked(7 ,2,0)" id = 7>1</button>
        </div>
        <div class="col">
            <button @click="clicked(8 ,2,1)" id = 8>1</button>
        </div>
        <div class="col">
            <button @click="clicked(9 ,2,2)" id = 9>1</button>
        </div>
      </div>
{{ display }}
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
        },
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
          alert("win")
        }else if(this.inputMetrix[1][0] == this.inputMetrix[1][1] && this.inputMetrix[1][0] == this.inputMetrix[1][2]){
          alert("win")
        }else if(this.inputMetrix[2][0] == this.inputMetrix[2][1] && this.inputMetrix[2][0] == this.inputMetrix[2][2]){
          alert("win")
        }else if(this.inputMetrix[0][0] == this.inputMetrix[1][0] && this.inputMetrix[1][0] == this.inputMetrix[2][0]){
          alert("win")
        }else if(this.inputMetrix[0][1] == this.inputMetrix[1][1] && this.inputMetrix[1][1] == this.inputMetrix[2][1]){
          alert("win")
        }else if(this.inputMetrix[0][2] == this.inputMetrix[1][2] && this.inputMetrix[1][2] == this.inputMetrix[2][2]){
          alert("win")
        }else if(this.inputMetrix[0][0] == this.inputMetrix[1][1] && this.inputMetrix[1][1] == this.inputMetrix[2][2]){
          alert("win")
        }else if(this.inputMetrix[0][2] == this.inputMetrix[1][1] && this.inputMetrix[1][1] == this.inputMetrix[0][2]){
          alert("win")
        }
      },
      clicked(e ,x,y){
        this.count ++;
        document.getElementById(e).disabled = true
        if(this.count % 2 ){
          document.getElementById(e).innerHTML = "X" 
          this.inputMetrix[x][y] = "X"
          this.winCheck()
          
        } else{
          document.getElementById(e).innerHTML = "O" 
          this.inputMetrix[x][y] = "O"
          this.winCheck()
        }
        
      }
    }
}
</script>


<style scoped>

</style>
