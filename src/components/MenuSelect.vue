<template>
<div class="temps">
  <label for="profession"> Profession : </label>
  <select name="select-profession" id="select-profession">
    <option value="Etudiant"> Étudiant </option>
    <option value="Etudiant"> Employé </option>
  </select>
  </div>
<select v-model="selected">
<option v-for="option in options" v-bind:value="option.value" v-bind:key="option.text" v-on:click="$emit('option.colorie')">
{{option.text}}
</option>
</select>


</template>

<script>



export default {
  
  name: 'MenuSelect',
  props: {
    msg: String
  },
  data () {
      
      return {
        
        selected: 'A',
        options: [
        { text : 'One', value :'A', colorie:"$emit(blue)" },
        { text : 'Two', value :'B', colorie:"$emit(yellow)" },
        { text : 'Three', value :'C', colorie:"$emit(purple)" },
      ]

  
    }
    }
};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


</style>
