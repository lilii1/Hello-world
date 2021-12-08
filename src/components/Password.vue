<template>
    <p>
      <label for="password">Mot de passe</label>
      <input type="password" value="" placeholder="Entrer le mot de passe" id="password" class="password">

    </p>
</template>

<script>




</script>

<style scoped>
form p { position: relative; }
label { 
  position: absolute;
  left:-9999px;
  text-indent: -9999px;
}
input {
  width: 250px;
  padding: 15px 12px;
  margin-bottom: 5px;
  border: 1px solid #e5e5e5;
  border-bottom: 2px solid #ddd;
  background: #f2f2f2;
  color: #555;
}

</style>