<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <form>
      <h3>Convidados</h3>
      <input type="number" min="0" placeholder="0" />
      <h3>Valor da Carne (Kg)</h3>
      <input type="number" step="0.01" min="0" placeholder="15,00" />
      <h3>Quantia por pessoa</h3>
      <select>
        <option value="300g">300g</option>
        <option value="350g">350g</option>
        <option value="350g">350g</option>
      </select>
      <button v-on:click="doStuff()">Calcular</button>
    </form>
  </div>
</template>

<script>
import Swal from "sweetalert2";

export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  methods: {
    doStuff() {
      let message = "Teste de Var";
      Swal.fire({
        position: "center",
        icon: "success",
        title: message,
        //showConfirmButton: false,
        timer: 1500,
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  font-size: 1.5rem;
}
h3 {
  font-size: 95%;
  margin: 2vh 0;
}
h4 {
  font-size: 95%;
  font-weight: 400;
  margin-top: 10px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
form {
  display: flex;
  flex-direction: column;
  align-items: center;
}
button {
  margin-top: 8vh;
  color: black;
  background: #ffcd45;
  border: none;
  padding: 10px;
  font-weight: 800;
  border-radius: 8%;
}
select {
  height: 4vh;
  width: 10vh;
  min-width: 70px;
  text-align: center;
  border-radius: 10%;
  background: #fafafa;
  border: 1px solid #ffbb00;
}
input {
  height: 4vh;
  text-align: center;
  width: 10vh;
  min-width: 70px;
  border-radius: 10%;
  border: none;
  background: #fafafa;
  outline: none;
  border: 1px solid #ffbb00;
}
</style>
