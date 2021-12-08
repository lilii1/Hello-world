<template>
<form id="App" 
    @submit="checkForm"
    method="post">

    <p v-if="errors.length">
      <b>Veuillez corriger les erreurs suivante(s):</b>
      <ul>
        <li v-for="error in errors" :key="error">{{ error }}</li>
      </ul>
    </p>

    <p>
      <label for="email">Mail:</label>
      <input name="email" type="email"  placeholder="Mail" v-model="email">
    </p>

    <p>
      <input type="submit" value="Vérifier les informations">
    </p>
  </form>
</template>

<script>


export default {
  name: 'App',
  components: {

  },
  data() {
    return {
      errors: [],
      email: null
    }
  },
  methods: {
    checkForm: function(e) {

      // Effacer les erreurs
      this.errors = [];

      // Vérifiez si l'e-mail n'est pas vide et correspond au modèle d'e-mail
      var re = /(^$|^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$)/;
      if (!this.email || !re.test(this.email))
      {
        this.errors.push("Votre email ne doit pas être vide et doit contenir '@' !");
      }

      if (!this.errors.length)
      {
        return true;
      }

      e.preventDefault();
    }
  }
}
</script>
<style scoped>
input[type="submit" i] {

    background-color: white;
    border-radius: 5px;
    border-color: aliceblue;
    padding: 5px;
   
}
input[type="submit" i]:hover {
   border-color: cornflowerblue;
}

input[type="email" i] {
  width: 250px;
  padding: 15px 12px;
  margin-bottom: 5px;
  border: 1px solid #e5e5e5;
  border-bottom: 2px solid #ddd;
  background: #f2f2f2;
  color: #555;

}
label { 
  position: absolute;
  left:-9999px;
  text-indent: -9999px;
}

</style>