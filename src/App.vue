<template>
  <div id="app">
    <HelloWorld msg="Advertisment Website"/>
    <img alt="Vue logo" src="./assets/sell.png">
    <div><button v-on:click="seen = true">Click to Sell your product here</button></div>
    <div v-if="seen">
      <br>
      <div>
        <label for="name">Name</label>
        <input style="margin-left:80px" id="name" v-model="name" type="text" name="name">
      </div>
      <br>
      <div>
        <label for="contact">Contact</label>
        <input style="margin-left:70px" id="contact" v-model="contact" type="text" name="contact">
      </div>
      <br>
      <div>
        <label for="itemName">Item Name</label>
        <input style="margin-left:45px" id="itemName" v-model="itemName" type="text" name="itemName">
      </div>
      <br>
      <div>
        <label for="itemDesc">Item Description</label>
        <input style="margin-left:10px" id="itemDesc" v-model="itemDesc" type="text" name="itemDesc">
      </div>
      <br>
      <div>
        <button v-on:click="checkForm()">Submit</button>
      </div>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  data: function () {
    return {
      seen : false,
      name : null,
      itemName : null,
      itemDesc : null,
      contact : null

    }
  },
  methods:{
    checkForm: function () {
      console.log(this.name+' is selling '+this.itemName+':'+this.itemDesc+'. Please contact: '+this.contact)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
