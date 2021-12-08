<template>
<form id="nom" 
    @submit="checkForm"
    method="post">

    <p v-if="errors.length">
      <b>Veuillez corriger les erreurs suivante(s):</b>
      <ul>
        <li v-for="error in errors" :key="error">{{ error }}</li>
      </ul>
    </p>

    <p>
      <label for="Nom">Nom:</label>
      <input name="Nom" type="text" placeholder="Nom" v-model="surname">
    </p>

    <p>
      <label for="prenom">Prénom:</label>
      <input name="prenom" type="text" placeholder="Prénom" v-model="firstname">
    </p>

    <p>
      <input type="submit" value="Vérifier les informations">
           <!-- <button v-on:click="step='step2' ,say('Merci pour vos coordonnées, il reste 3 étapes'), type="submit" value="submit"">Valider</button>-->
           <!--J'ai voulu faire un seul bouton qui vérifie les actions pour le nom et le prénom puis qui passe à la "step2" en même temps, mais je n'ai pas réussi-->

    </p>
  </form>
</template>

<script>


export default {
  name: '#Nom',
  components: {

  },
  data() {
    return {
      errors: [],
      surname: null,
      firstname: null,
      
    }
  },
  methods: {
    checkForm: function(e) {

      // Effacer les erreurs
      this.errors = [];

      // Vérifiez si le nom n'est pas vide et la longueur <= 10
      if (!this.surname || this.surname.length > 10)
      {
        this.errors.push("Le nom de famille ne peut pas être vide et doit avoir une longueur <= 10 !");
      }

      // Vérifiez si le prénom n'est pas vide et la longueur <= 10
      if (!this.firstname || this.firstname.length > 10)
      {
        this.errors.push("Le prénom ne peut pas être vide et doit avoir une longueur <= 10 !");
      }

      e.preventDefault();
    }
  }
}

</script>

<style scoped>
label { 
  position: absolute;
  left:-9999px;
  text-indent: -9999px;
}
input[type="submit" i] {

    background-color: white;
    border-radius: 5px;
    border-color: aliceblue;
    padding: 5px;
   
}
input[type="submit" i]:hover {
   border-color: cornflowerblue;
}

input[type="text" i] {

width: 250px;
  padding: 15px 12px;
  margin-bottom: 5px;
  border: 1px solid #e5e5e5;
  border-bottom: 2px solid #ddd;
  background: #f2f2f2;
  color: #555;
  
}

</style>
