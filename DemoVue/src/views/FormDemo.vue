<template>
  <h1>Drop-down List in Vue</h1>
  <form @submit.prevent="registerAnswer">
  {{message}}
    <label for="cars">Choose a car:</label> 
    <select  v-model="carSelected" id="cars">
      <option disabled value="">Please select one</option>
      <option>Volvo</option>
      <option>Saab</option>
      <option>Opel</option>
      <option>Audi</option>
    </select>
    <br><br>
    <input type="submit" value="Submit">
  </form>
  <div>
  {{valueMsgPrint()}}
    <h3>Submitted answer:</h3>
    <p id="pAnswer">{{ inpValSubmitted }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      carSelected: '',
      message:'this is personal message',
      inpValSubmitted: 'Not submitted yet'
    }
  },
  methods: {
    registerAnswer() {
      if(this.carSelected) {
        this.inpValSubmitted = this.carSelected;
      }
      },
      valueMsgPrint(){
      const carValue= 'hello how are you'
      return carValue;
    }
  }
}

</script>
<style scoped>
  div {
    border: dashed black 1px;
    border-radius: 10px;
    padding: 0 20px 20px 20px;
    margin-top: 20px;
    display: inline-block;
  }
  button {
    margin: 10px;
  }
  label {
    width: 80px;
    padding: 5px;
  }
  label:hover {
    cursor: pointer;
    background-color: rgb(211, 244, 211);
    border-radius: 5px;
  }
  #pAnswer {
    background-color: lightgreen;
    padding: 5px;
  }
</style>                