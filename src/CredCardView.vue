<template>
  <div class="h-screen w-screen bg-pink-100">
    <div class="container mx-auto grid grid-cols-2 h-full">
      <div class="flex flex-col items-center justify-center mt-28">
        <div class="bg-gray-200 shadow-xl p-6 w-[80%] relative">
          <div
            class="bg-gray-100 h-[220px] w-[55%] rounded-[25px] shadow-xl absolute -top-[22%] left-[22%]"
          >
            cartao
          </div>
          <form action="">
            <div class="flex flex-col mt-[150px]">
              <label for="name">Final Number:</label>
              <input
                type="text"
                class="p-2"
                placeholder="Choose your four lastest number"
              />
            </div>
            <div class="flex flex-col my-8">
              <label for="name">Card Name:</label>
              <input type="text" placeholder="Type your name" class="p-2" />
            </div>
            <div class="grid grid-cols-3">
              <div>
                <label for="" class="block">Expiration Date</label>
                <select name="mes" id="mes">
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
                <select name="ano" id="ano">
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
                <input type="text" class="p-2" />
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
          <div>
            <h1 class="text-5xl font-bold text-[#256cd1] text-center">
              Aqui você escolhe a personalidade do seu cartão!
            </h1>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped></style>
