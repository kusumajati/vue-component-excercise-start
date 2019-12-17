<template>
  <div id="app">
    <div>
      <h1> Header (Parent Component) </h1>
    </div>
    <hr>
    <div>
      <h3> Show Developer (child component)</h3>
      <p>Developer: {{showName}}</p>
      <p>Languages: <span v-for="(lang, index) in languages" :key="index" >
         <span v-if="lang.checked == true"> {{lang.name}},</span> 
        </span> </p>
    </div>
    <hr>
    <h3>Edit Developer (child component)</h3>
    <input type="text" placeholder="developer name" v-model="name">
    <button @click="changeName()">Change Name</button>
    <br><br>

    <li id="lang" v-for="(lang, index) in languages" :key="index">
          <label for="lang">
      <input type="checkbox" @click="clicked(lang)">
        <span>{{lang.name}}</span>
    </label>
    </li>

  </div>
</template>

<script>
export default {
  data(){
    return{
      showName:'',
      name:'',
      languages:[
        {name:'Javascript', checked:false },
        {name:'Ruby', checked:false },
        {name:'Python', checked:false },
        {name:'Java', checked:false },
        {name:'Swift', checked:false }
      ]
    }
  },
  methods:{
    changeName(){
      this.showName = this.name
    },
    clicked(lang){
      lang.checked = !lang.checked
    }
  }
}
</script>

<style>
.red{
  color: red;
}
</style>
