<template>
    <div>enter name:
          <input type="text" name="" id="" v-model="name">
          <button v-on:click="setUser(name)">submit</button></div>
</template>
<script>
export default {
    name:'childComp2',
    data(){
        return{
             
            name:'',
            
             
        }
    },
    props:{
         
      
            setUser:Function
        
    },
    
}
</script>