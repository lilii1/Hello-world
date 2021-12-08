<template>
<label for="start">Date de naissance:</label>

<input type="date" id="start" name="trip-start"
       value="2021-11-22"
       min="2020-01-01" max="2025-12-31">
</template>

<script>



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button {
display: flex;
    margin-left: auto;
    margin-right: auto;
    margin-top: 40px;
}

#start{
  margin-left: 10px;
  margin-top: 30px;
}

input[type="date" i] {
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
