<template>
  <div class="row container" >
    <div class="col-6 border ml-5">

      <div class="row">
        <div class="col">
            <button @click="clicked()">1</button>
        </div>
        <div class="col">
            <button @click="clicked()">1</button>
        </div>
        <div class="col">
            <button @click="clicked()">1</button>
        </div>
      </div>

      <div class="row">
        <div class="col">
            <button @click="clicked()">1</button>
        </div>
        <div class="col">
            <button @click="clicked()">1</button>
        </div>
        <div class="col">
            <button @click="clicked()">1</button>
        </div>
      </div>

      <div class="row">
        <div class="col">
            <button @click="clicked()">1</button>
        </div>
        <div class="col">
            <button @click="clicked()">1</button>
        </div>
        <div class="col">
            <button @click="clicked()">1</button>
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
        
      }
    },
    computed: {
       
    },
    methods:{
      clicked(){
        alert('clicked')
      }
    }
}
</script>


<style scoped>

</style>
