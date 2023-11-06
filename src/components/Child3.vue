<template>
  <div>
    <h2 class="hi">using computed : {{ getrandom1 }}</h2>
    <h3 >using method : {{ getrandomno() }}</h3>

    <h2 class="hi">using computed : {{ getrandom1}}</h2>
  
    <h3 >using method : {{ getrandomno() }}</h3>
    <h2 class="hi">using computed : {{ getrandom1}}</h2>
    <br>
    <p>this is for computed get</p>
    <input type="text" v-model="fullname">
    <h2>Firstname :{{name}}</h2>
    <h2>Lastname : {{lastname}}</h2>
    <br>
    <hr>
     
  </div>
</template>
<script>

// here computed method will return same value across All
// while methods will return diffrent values 
export default {
  name: "childComp3",
  data() {
    return {
        name:"jacob",
        lastname:"smith",
         
    };
  },
  methods: {
    getrandomno() {
      return Math.random();
    },
  },
  computed: {
    getrandom1: function () {
      return Math.random();
    },
    fullname:{
        get:function()
        {
            return this.name+" "+this.lastname;
        } ,
        set:function(name)
        {
            var gname=name.split("");
            this.name=gname[0];
            this.lastname=gname[1];
        }
    },
    
  },
};
</script>
<style  scoped>
 .hi{
    height: 40px;
    background-color: green;
    overflow: hidden;
}
</style>