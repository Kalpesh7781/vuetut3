<template>
  <div>
     <p>Wathch Properties </p>
     <!-- it will change data automatically when cahnges are made -->
     Kilometers : <input type="text" name="" id="" v-model="kilometers">
     Meters : <input type="text" name="" id="" v-model="meters" >
     
  </div>
</template>
<script>


export default {
  name: "childComp3",
  data() {
    return {
       kilometers:'',
       meters:'',
         
    };
  },
  watch:
  {
    kilometers:function(val)
    {
        this.kilometers=val;
        this.meters=val*1000;

    },
    meters:function(val)
    {
        this.kilometers=val/1000;
        this.meters=val;
    }
  }
   
   
};
</script>
<style  scoped>
  
</style>