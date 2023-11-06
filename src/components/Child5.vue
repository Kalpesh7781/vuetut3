<template>
  <div>
     <div id = "databinding">  
         <div v-bind:style = "styleobj" v-on:mouseover = "changebgcolor" v-on:mouseout = "originalcolor"></div>  
         <input type="text" v-on:keyup.enter="esec" name="team" id="team" placeholder="enter team name">
         <h2>team: {{team}}</h2>
      </div>  
     
  </div>
</template>
<script>


export default {
  name: "childComp5",
  data() {
    return {
      styleobj : {  
         width:"100px",  
         height:"100px",  
         backgroundColor:"red"  
      },
      team:'',  
    };
  },
   methods : {  
      changebgcolor : function() {  
         this.styleobj.backgroundColor = "blue";  
      },  
      originalcolor : function() {  
         this.styleobj.backgroundColor = "brown";  
      } ,
      esec:function(event)
      {
        this.team=event.target.value;

      }

   },  
   
   
};
</script>
<style  scoped>
  div
  {
    position: relative;
    left: 15%;
  }
</style>