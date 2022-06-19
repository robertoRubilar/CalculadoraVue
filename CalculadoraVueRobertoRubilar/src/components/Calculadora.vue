<template>
  <div class="p-3" style="max-width: 400px; margin: 50px auto; background: #345">
  
   <div class="w-full rounded m-1 p-3 text-right lead font-weight-bold text-white bg-vue-dark">
     {{resultado || 0 }}
    </div>
  
  <div class="row no-gutters">
      <div class="col-3" v-for="n in operadores" :key="n">
       <div class="lead text-white text-center m-1 py-3 bg-vue-dark rounded hover-class"
          :class="{'bg-vue-blue': ['C','*','/','-','+','%','='].includes(n)}" @click="action(n)">
          {{n}}
        </div>
      </div>
    </div>

  
  </div>
</template>

<script>
export default {
  name: 'Calculator',
  props: {
    msg: String
  },
  data() {
    return {
      resultado: '',
      operadores: ['C','*','/','-',7,8,9,'+',4,5,6,'%',1,2,3,'=',0,'.']
    }
  },


  methods:{
    action(n){
 if(!isNaN(n) || n === '.'){
        this.resultado += n + '';
      }
    }
  }
  }
</script>

<style scoped>
.bg-vue-dark{
  background: #12345e

}


.hover-class:hover{
cursor: pointer;

background:#40B4C6;
}

 .bg-vue-blue {
    background: #40B4C6; 
  }


</style>
