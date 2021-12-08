<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
<h1 :style="{color:colorie}">Coucou</h1>
<div v-if="step === 'step1'">
  <h1 :style="{color:colorie}">Inscription</h1>
    <RadioButtons msg="" />
    <Password msg="" />
    <TextInput msg="" />
    <CheckBox msg="" />
     <button v-on:click="colorie='pink'">Changer la couleur</button>
      <button v-on:click="step='step2' ,say('Merci pour vos coordonnées, il reste 3 étapes')">Valider</button>
</div>

  <div v-if="step === 'step2'">
    <h1>Informations supplémentaires</h1>
      <DateInput msg="" />
      <Phone msg="" />
      <Email msg=""/>
        <button v-on:click="step='step3',say('Il reste 2 étapes')">Valider</button>
  </div>

  <div v-if="step === 'step3'">
    <h1>Paiement information</h1>
      <RadioPaye msg="" />
      <Text msg="" />
      <ExpireDate msg="" />
        <button v-on:click="step='step4',say('Il reste 1 étape')">Valider</button>
  </div>
 
 <div v-if="step === 'step4'">
   <Liste msg=""/>
 <SearchAutocomplete msg="" />
  <div id="app">
    <SearchAutocomplete
      :items="[
        'Apple',
        'Banana',
        'Orange',
        'Mango',
        'Pear',
        'Peach',
        'Grape',
        'Tangerine',
        'Pineapple'
      ]"
    />
  </div>
   <button v-on:click="say('Toutes vos informations sont enregistrées, merci de votre')">Valider</button>

 </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TextInput from './components/TextInput.vue'
import DateInput from './components/DateInput.vue'
import RadioButtons from './components/RadioButtons.vue'
import CheckBox from './components/CheckBox.vue'
import Password from './components/Password.vue'
import RadioPaye from './components/RadioPaye.vue'
import ExpireDate from './components/ExpireDate.vue'
import Text from './components/Text.vue'
import Email from './components/Email.vue'
import Phone from './components/Phone.vue'
import SearchAutocomplete from './components/SearchAutocomplete.vue'
import Liste from './components/Liste.vue'






export default {
  name: 'App',
  components: {
    HelloWorld,
    TextInput,
    DateInput,
    RadioButtons,
    CheckBox,
    Password,
    RadioPaye,
    ExpireDate,
    Text,
    Email,
    Phone,
   SearchAutocomplete,
   Liste
    
  },
  data() {
    return{
      colorie: 'Green',
      step:'step1',
      alert:'vos informations ont été enregistré'
    }
  },
   methods: {
    say: function (message) {
      alert(message)
    }
  }

}
 
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.label{
      margin-left: 40px;
      padding: 10px;
}
button{
      margin-top: 30px;
      margin-bottom: 60px;
    background-color: white;
    border-radius: 5px;
    border-color: aliceblue;
    margin-right: 20px;
    padding: 5px;


}
button:hover{
  border-color: cornflowerblue;
}

</style>
