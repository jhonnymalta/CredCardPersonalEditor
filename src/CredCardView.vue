<template>
  <div class="h-screen w-screen bg-[#49256c]">
    <div class="container mx-auto grid grid-cols-2 h-full">
      <div class="flex flex-col items-center justify-center mt-28">
        <div class="bg-gray-200 shadow-xl p-6 w-[80%] relative">
          <div
            class="h-[220px] w-[55%] rounded-[25px] shadow-xl absolute -top-[22%] left-[22%]"
            :class="colorList[1]"
          >
            <div class="flex flex-col p-4 justify-center relative">
              <div class="flex items-center">
                <img
                  src="src\assets\cardChip.png"
                  alt="METALIC CHIP"
                  class="h-[33px] mt-4 ml-4"
                />
                <img
                  src="src\assets\wifi_icon.svg"
                  alt="APPROACH CHIP"
                  class="h-[25px] mt-4 ml-4 -rotate-90"
                />
              </div>
              <div>
                <img
                  :src="flagPath[flagUsed]"
                  alt="Card Flag"
                  class="h-[33px] absolute right-5 top-5"
                />
              </div>
              <span class="text-center text-2xl font-bold text-white mt-8">{{
                cardNumber
              }}</span>
              <span class="text-1xl font-bold text-white mt-3 ml-4"
                >{{ cardName.toUpperCase() }}
              </span>
              <div class="flex justify-between">
                <div class="flex flex-col">
                  <span class="text-white ml-4 text-[0.8em]">Validate</span>
                  <span class="text-white ml-12">{{ mes }}/{{ ano }}</span>
                </div>
                <div class="flex flex-col">
                  <span class="text-white text-[0.8em]">CVV</span>
                  <span class="text-white ml-9">{{ cvv }}</span>
                </div>
              </div>
            </div>
          </div>
          <form action="">
            <div class="flex flex-col mt-[150px]">
              <label for="name">Number:</label>
              <input
                type="text"
                class="p-2"
                placeholder="Choose your card number"
                v-model="cardNumber"
              />
            </div>
            <div class="flex flex-col my-8">
              <label for="name">Card Name:</label>
              <input
                type="text"
                placeholder="Type your name"
                class="p-2"
                v-model="cardName"
              />
            </div>
            <div class="grid grid-cols-3 gap-6">
              <div>
                <label for="" class="block">Expiration Date</label>
                <select
                  name="mes"
                  id="mes"
                  class="bg-white h-10 w-full text-start pl-2"
                >
                  <option value="01">Janeiro</option>
                  <option value="02">Fevereiro</option>
                  <option value="03">Março</option>
                  <option value="04">Abril</option>
                  <option value="05">Maio</option>
                  <option value="06">Junho</option>
                  <option value="07">Julho</option>
                  <option value="08">Agosto</option>
                  <option value="09">Setembro</option>
                  <option value="10">Outubro</option>
                  <option value="11">Novembro</option>
                  <option value="12">Dezembro</option>
                </select>
              </div>
              <div>
                <label for="" class="block"><br /></label>
                <select
                  name="ano"
                  id="ano"
                  class="bg-white h-10 w-full text-start pl-2"
                >
                  <option value="01">2024</option>
                  <option value="02">2025</option>
                  <option value="03">2026</option>
                  <option value="04">2027</option>
                  <option value="05">2028</option>
                  <option value="06">2029</option>
                  <option value="07">2030</option>
                  <option value="08">2031</option>
                  <option value="09">2032</option>
                  <option value="10">2033</option>
                  <option value="11">2034</option>
                  <option value="12">2035</option>
                </select>
              </div>
              <div class="flex flex-col">
                <label for="" class="block">CVV</label>
                <input type="text" class="p-2" v-model="cvv" />
              </div>
            </div>
            <div>
              <input
                type="submit"
                class="bg-cyan-500 text-white w-full py-2 mt-10 rounded"
                value="Submit"
              />
            </div>
          </form>
        </div>
      </div>
      <div>
        <div class="flex flex-col items-center">
          <div class="mt-16">
            <h1 class="text-6xl font-bold text-[#f0c902] text-start">
              Here<br />
              you choose the personality of your card!
            </h1>
          </div>
        </div>
        <div class="flex mt-10 justify-between">
          <div class="flex flex-col items-center">
            <label for="elo">
              <img
                src="src\assets\elo-logo.svg"
                alt="Card Flag"
                class="h-16 mb-4"
              />
            </label>
            <input
              type="radio"
              name="flag"
              value="0"
              id="elo"
              v-model="flagUsed"
            />
          </div>
          <div class="flex flex-col items-center">
            <label for="amex">
              <img
                src="src\assets\amex-american-express-logo.svg"
                alt="Card Flag"
                class="h-16 mb-4"
              />
            </label>
            <input
              type="radio"
              name="flag"
              value="1"
              id="amex"
              v-model="flagUsed"
            />
          </div>
          <div class="flex flex-col items-center">
            <label for="master">
              <img
                src="src\assets\mc_symbol.svg"
                alt="Card Flag"
                class="h-16 mb-4"
              />
            </label>
            <input
              type="radio"
              name="flag"
              value="2"
              id="master"
              v-model="flagUsed"
            />
          </div>

          <div class="flex flex-col items-center">
            <label for="visa">
              <img
                src="src\assets\visa.png"
                alt="Card Flag"
                class="h-16 mb-4"
              />
            </label>
            <input
              type="radio"
              name="flag"
              value="3"
              id="visa"
              class=""
              v-model="flagUsed"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const cardNumber = ref("################");
const cardName = ref("Fulâno M DA Silva");
const cvv = ref("123");
const ano = ref(24);
const mes = ref();

let colorList = ["cardColor001", "cardColor002"];
const flagUsed = ref(0);
const flagPath = ref([
  "src/assets/elo-logo.svg",
  "src/assets/amex-american-express-logo.svg",
  "src/assets/mc_symbol.svg",
  "src/assets/visa.png",
]);
</script>

<style scoped>
.cardColor001 {
  background: #00d0e0; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    #018b95,
    #00d0e0
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    #018a93,
    #00d0e0
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

  box-shadow: -10px 10px 20px 0.22rem #4040407e;
}
.cardColor002 {
  background: #e000d5; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    rgb(127, 3, 131),
    #e000d5
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    rgb(127, 3, 131),
    #e000d5
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

  box-shadow: -10px 10px 20px 0.22rem #4040407e;
}
</style>
