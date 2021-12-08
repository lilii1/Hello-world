<template>
    <div class="form-group">
								<label for="honame" class="wizard-form-text-label">Nom apparaissant sur la carte</label>
								<input type="text" class="form-control wizard-required" id="honame" placeholder="Nom apparaissant sur la carte"> 
								<div class="wizard-form-error"></div>
							</div>
<div class=card>
    <p>Numéro de carte</p>
    <p>{{msg}}</p> <input type="text" placeholder="Numéro de carte"/>
</div>

<div class=cvc>
<p>CVC</p>
<p>{{msg}}</p> <input type="text" placeholder="CVC"/>
</div>

</template>

<style scoped>

.card{
        display: flex;
    justify-content: center;
    margin-top: 30px;
    margin-bottom: 20px;
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
.cvc{

    display: inline-flex;

}
label { 
  position: absolute;
  left:-9999px;
  text-indent: -9999px;
}

p{
    position: absolute;
  left:-9999px;
  text-indent: -9999px; 
}

</style>