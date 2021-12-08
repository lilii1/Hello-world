<template>
<div class="buttons">
      
     <button v-on:click="$emit('validation')">Validation</button>
      
             <button onclick="alert('Votre formulaire à été réinitialisé ')">Réinitialiser </button>

      </div>
</template>

<script>

export default {
      name: "Button",
      props: {
            msg: String,
      },
      data(){
            return
      }
}

  


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
