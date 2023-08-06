<script setup>

import {reactive} from "vue";

const data = reactive(
  {
    depositedAmount: 0,
    withdrawAmount: 0,
    balanceAmount: 1240,
    newDeposit: null,
    newWithdraw: null,

  }
)

function addNewDeposit(){
   data.depositedAmount += parseInt(data.newDeposit);
  data.balanceAmount += parseInt(data.newDeposit)
}

function getNewWithdraw(){
  data.withdrawAmount += parseInt(data.newWithdraw)
  data.balanceAmount -= parseInt(data.newWithdraw)
}


</script>

<template>
  <header>
    <h1 class="text-5xl text-center mt-4">Amar <span class="text-red-500 font-medium">Bank</span>!!!</h1>
  </header>
  <main>

    <section class="mt-8">
      <div class="grid grid-cols-3 gap-4 w-3/4 mx-auto text-white">
        <div class="bg-yellow-400 p-8 rounded-lg">
          <h4 class="text-3xl">Deposit</h4>
          <h2 id="deposit-total"  class="text-5xl font-medium">$<span  >{{data.depositedAmount}}</span></h2>
        </div>
        <div class="bg-red-400 p-8 rounded-lg">
          <h4 class="text-3xl">Withdraw</h4>
          <h2 class="text-5xl font-medium">$<span id="withdraw-total">{{ data.withdrawAmount }}</span></h2>
        </div>
        <div class="bg-blue-400 p-8 rounded-lg">
          <h4 class="text-3xl">Balance</h4>
          <h2 class="text-5xl font-medium">$<span id="balance-total">{{data.balanceAmount}}</span></h2>
        </div>
      </div>
    </section>

    <section class="mt-8 w-3/4 mx-auto">
      <div class="grid grid-cols-2 gap-4">
        <div class="bg-violet-400 p-8 rounded-lg">
          <h3 class="text-4xl text-white mb-4">Your Deposit</h3>
          <input v-model="data.newDeposit" id="deposit-field" class="w-3/4 px-4 py-3 rounded block" type="text" placeholder="$ Amount  you want to deposit">
          <button @click="addNewDeposit()"  id="btn-deposit" class="bg-blue-800 px-6 py-2 text-white rounded-lg mt-4 font-medium hover:bg-blue-600">Deposit</button>
        </div>
        <div class="bg-amber-400 p-8 rounded-lg">
          <h3 class="text-4xl text-white mb-4">Your Withdraw</h3>
          <input v-model="data.newWithdraw"  id="withdraw-field" class="w-3/4 px-4 py-3 rounded block" type="text" placeholder="$ Amount  you want to withdraw">
          <button @click="getNewWithdraw()" id="btn-withdraw" class="bg-blue-800 px-6 py-2 text-white rounded-lg mt-4 font-medium hover:bg-blue-600">Withdraw</button>
        </div>
      </div>
    </section>
  </main>

</template>

<style scoped>
</style>
