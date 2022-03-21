<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <form>
      <h3>Convidados</h3>
      <input type="number" min="0" id="peoples" value="0" />
      <h3>Valor da Carne (Kg)</h3>
      <input type="number" step="0.01" min="0" placeholder="0,00" id="price" />
      <h3>Quantia por pessoa</h3>
      <select id="weight">
        <option value="300" selected>300g</option>
        <option value="350">350g</option>
        <option value="400">400g</option>
      </select>
      <button @click="calulate()">Calcular</button>
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
      let message = "";
      Swal.fire({
        position: "center",
        icon: "success",
        title: message,
        //showConfirmButton: false,
        //timer: 1500,
      });
    },
    calulate() {
      //Number of Peoples
      let operator, result, pricepeople, pricetotal, message;
      let peopleNumber = 0;
      peopleNumber = document.querySelector("#peoples");
      console.log(peopleNumber.value);

      //Price of Meat
      let price = "";
      price = document.querySelector("#price");
      console.log(price.value);

      //Amount of Meat
      let select = document.getElementById("weight");
      let weight = select.options[select.selectedIndex].value;
      console.log(weight);
      if (price.value == "" || peopleNumber.value == "") {
        Swal.fire({
          position: "center",
          icon: "error",
          title: "Preencha todos os campos",
          showCloseButton: true,
          showCancelButton: true,
          showConfirmButton: false,
          cancelButtonColor: "#dc3741",
          cancelButtonText: "Fechar",
          //showConfirmButton: false,
          //timer: 1500,
        });
      } else if (weight == 300) {
        operator = 0.3;
        result = peopleNumber.value * operator;
        pricepeople = price.value * operator;
        pricetotal = pricepeople * peopleNumber.value;
        message = `Selecionado 300 gramas!
      Total da compra:${result} Kgs
      R$ ${pricepeople}  por pessoa
      R$ ${pricetotal}  Total da compra
      `;
        console.log(message);
        Swal.fire({
          position: "center",
          icon: "success",
          title: message,
          showCloseButton: true,
          showCancelButton: true,
          showConfirmButton: false,
          cancelButtonColor: "#4CAF50",
          //showConfirmButton: false,
          //timer: 1500,
        });
      } else if (weight == 350) {
        operator = 0.35;
        result = peopleNumber.value * operator;
        pricepeople = price.value * operator;
        pricetotal = pricepeople * peopleNumber.value;
        message = `Selecionado 350 gramas!
      Total da compra:${result} Kgs
      R$ ${pricepeople}  por pessoa
      R$ ${pricetotal}  Total da compra
      `;
        console.log(message);
        Swal.fire({
          position: "center",
          icon: "success",
          title: message,
          showCloseButton: true,
          showCancelButton: true,
          showConfirmButton: false,
          cancelButtonColor: "#4CAF50",
          //showConfirmButton: false,
          //timer: 1500,
        });
      } else if (weight == 400) {
        operator = 0.4;
        result = peopleNumber.value * operator;
        pricepeople = price.value * operator;
        pricetotal = pricepeople * peopleNumber.value;
        message = `Selecionado 400 gramas!
      Total da compra:${result} Kgs
      R$ ${pricepeople}  por pessoa
      R$ ${pricetotal}  Total da compra
      `;
        console.log(message);
        Swal.fire({
          position: "center",
          icon: "success",
          title: message,
          showCloseButton: true,
          showCancelButton: true,
          showConfirmButton: false,
          cancelButtonColor: "#4CAF50",
          //timer: 1500,
        });
      }
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
