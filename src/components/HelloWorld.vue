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
    calulate() {
      //Number of Peoples
      let operator, result, pricepeople, pricetotal, message;
      let peopleNumber = 0;
      peopleNumber = document.querySelector("#peoples");

      //Price of Meat
      let price = "";
      price = document.querySelector("#price");

      //Amount of Meat
      let select = document.getElementById("weight");
      let weight = select.options[select.selectedIndex].value;
      if (price.value == "" || peopleNumber.value == "") {
        Swal.fire({
          position: "center",
          icon: "error",
          title: "Preencha todos os campos",
          timer: 1500,
          showCancelButton: false,
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
        message = `Orçamento do Churras:

      Total de Carne:${result} Kg
      Valor por Pessoa: R$ ${pricepeople}
      Total da compra: R$ ${pricetotal}
    `;
        Swal.fire({
          position: "center",
          icon: "success",
          title: message,
          showConfirmButton: false,
          showCancelButton: true,
          showDenyButton: true,
          denyButtonColor: "#4CAF50",
          cancelButtonText: "Copiar Orçamento",
          denyButtonText: "Enviar pelo whats",
        }).then((result) => {
          if (result.isDismissed) {
            navigator.clipboard.writeText(message);
            Swal.fire("Copiado com sucesso!", "", "success");
          } else if (result.isDenied) {
            window.open(
              "https://api.whatsapp.com/send?phone&text=" + message,
              "_blank"
            );
          }
        });
      } else if (weight == 350) {
        operator = 0.35;
        result = peopleNumber.value * operator;
        pricepeople = price.value * operator;
        pricetotal = pricepeople * peopleNumber.value;
        message = `Orçamento do Churras:

      Total de Carne:${result} Kg
      Valor por Pessoa: R$ ${pricepeople}
      Total da compra: R$ ${pricetotal}
    `;
        Swal.fire({
          position: "center",
          icon: "success",
          title: message,
          showConfirmButton: false,
          showCancelButton: true,
          showDenyButton: true,
          denyButtonColor: "#4CAF50",
          cancelButtonText: "Copiar Orçamento",
          denyButtonText: "Enviar pelo whats",
        }).then((result) => {
          if (result.isDismissed) {
            navigator.clipboard.writeText(message);
            Swal.fire("Copiado com sucesso!", "", "success");
          } else if (result.isDenied) {
            window.open(
              "https://api.whatsapp.com/send?phone&text=" + message,
              "_blank"
            );
          }
        });
      } else if (weight == 400) {
        operator = 0.4;
        result = peopleNumber.value * operator;
        pricepeople = price.value * operator;
        pricetotal = pricepeople * peopleNumber.value;
        message = `Orçamento do Churras:

      Total de Carne:${result} Kg
      Valor por Pessoa: R$ ${pricepeople}
      Total da compra: R$ ${pricetotal}
    `;
        Swal.fire({
          position: "center",
          icon: "success",
          title: message,
          showConfirmButton: false,
          showCancelButton: true,
          showDenyButton: true,
          denyButtonColor: "#4CAF50",
          cancelButtonText: "Copiar Orçamento",
          denyButtonText: "Enviar pelo whats",
        }).then((result) => {
          if (result.isDismissed) {
            navigator.clipboard.writeText(message);
            Swal.fire("Copiado com sucesso!", "", "success");
          } else if (result.isDenied) {
            window.open(
              "https://api.whatsapp.com/send?phone&text=" + message,
              "_blank"
            );
          }
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
