<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>message length : {{msg.length}}</p>
    <h3>{{getinfo()}}</h3>
    <hr>
     <button v-on:dblclick="test('this is simple')">alert</button>
     <h3>function values : name =  {{getdetails().name}} hobby:  {{getdetails().hobby}}</h3>

     <h3>passing data from temp - name : {{show("dev")}}</h3>
     <br>
     <button v-on:click ="increment()">Count +</button>
     <h3>count is : {{count}}</h3>
     <hr>
     <h2>Two way binding example</h2>
     <input type="text" v-model="hometown">
     <br>
     <h3>hometown is : {{hometown}}</h3>
     <hr>
     <p>enter 1 num</p>
     <input type="number" name="" id="" v-model="num1">
     <p>enter 2 num</p>
     <input type="number" name="" id="" v-model="num2">
     <br>
     <button v-on:click="getsum()">sum</button>
     <br>
     <hr>
     <h1>checkbox double binding</h1>
     <p>technology</p>
     <label for="java">java</label>
     <input type="checkbox" name="java" v-model="technology" value="java">

     <label for="php">php</label>
     <input type="checkbox" name="php" v-model="technology" value="php">

     <label for="node">node</label>
     <input type="checkbox" name="node" v-model="technology" value="node">
     <br>
     <h3>seleced technology : {{technology}}</h3>
     <br>
     <hr>
     <p>select role</p>
     <label for="admin">admin</label>
     <input type="radio" name="" id="" v-model="role" value="admin">
     <label for="teacher">Teacher</label>
       <input type="radio" name="" id="" v-model="role" value="teacher">
       <label for="student">Student</label>
        <input type="radio" name="" id="" v-model="role" value="student     ">
        <br>
        <h3>Your role : {{role}}</h3>
        <br>
        <hr>
        <h2>days of week</h2>
        <ul v-for="x in days" :key="x">{{x}}</ul>
        <h2>flower and their colors</h2>
        <ul v-for="x in flowers" :key="x">{{x.name}}  :  {{x.color}} </ul>
        <br>
        <hr>
        <h2>passing value to child </h2>
        <childComp :flowers="flowers" />
        <hr>
        <h2>getting data from child</h2>
        <h2></h2>
        <childComp2 :setUser="setUser" />
        <h2>{{uname}}</h2>
        <hr>
        <h2>COmputed properties</h2>
        <childComp3 />
        <hr>
        <childComp4 />
        <hr>
         <childComp5 />
         <hr>
         




  </div>
</template>

<script>
import childComp from './Child.vue'
import childComp2 from './Child2.vue'
import childComp3 from './Child3.vue'
import childComp4 from './Child4.vue'
import childComp5 from './Child5.vue'

export default {
  name: 'HelloWorld',
  props: { /*using this propery we can acess data that are passed by parent element to child element */
    msg: String
  },
  data(){  /*using this we can passe data to template  */
    return{
      name:"kalpesh",
      uname:"",
      email:'xyz@gamao.com',
      getinfo:function()
      {
        return "my name is : "+this.name+"\n my email is : "+this.email;
      },
      count:0,
      hometown:'',
      num1:0,
      num2:0,
      technology:[],
      role:"",
      days:["sun","mon","tue","thur"],
      flowers:[{
        name:"rose",
        color:"pink"
      },
      {
        name:"mogra",
        color:"white"
      },
      {
        name:"sunflower",
        color:"maroon"
      }]



    }
  },
  methods:
  {
    setUser(name)
    {
     this.uname=name;
    },
    test(data){
      alert(data);
    },
    getsum()
    {
      return alert(this.num1+this.num2);
    },
    getdetails()
    {
      return{
        name:"radha",
        hobby:"reading"
      }

    },
    show(name){
      return name;
    },
    increment()
    {
      return this.count=this.count+1;
    }
  },
  components:
  {
    childComp,
    childComp2,
    childComp3,
    childComp4,
    childComp5

  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
