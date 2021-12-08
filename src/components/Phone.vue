<template>
  <div class="hello">
    <p style="position: absolute;
  left:-9999px;
  text-indent: -9999px;">Téléphone :</p>
    <input type="text" placeholder="Saisir le numéro de téléphone" v-model="mynumber"  @input="change($event)"
      @change="change($event)"/>
    <div class="error" v-if="!isValid">Numéro de téléphone invalide</div>
  </div>
</template>

<script>
export default {
  name: "InputNumberError",
  data() {
    return {
      mynumber: "",
      isValid: true,
      regex: /[0-9]/
    };
  },
  methods: {
    change:function(e){
      const number = e.target.value
      this.isNumberValid(number);
    },
    isNumberValid: function(inputNumber) {
      this.isValid=   this.regex.test(inputNumber)
    }
  }
};
</script>

<style scoped>
.error{
  color:red;
}
.hello{
    display: flex;
    justify-content: center;

}

input[type="text" i] {

    height: 20px;
    margin-top: 14px;
    margin-left: 10px;
    width: 250px;
    padding: 15px 12px;
    margin-bottom: 5px;
    border: 1px solid #e5e5e5;
    border-bottom: 2px solid #ddd;
    background: #f2f2f2;
    color: #555;

}


</style>