<template>
    <div>
        <li v-for="x in flowers" :key="x" >
         {{x.name}} :
          {{x.color}} </li>
          
          <h5>thats it</h5>
          <h5>{{show()}}</h5>

 
    </div>
</template>
<script>
export default {
    name:'childComp',
    data(){
        return{
             
          
            show:function()
            {
                console.log();
            },
             
        }
    },
    props:{
         
            flowers:Object,
            
        
    },
    
}
</script>