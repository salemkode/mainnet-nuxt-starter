<template>
  <div>Address: {{ address }}</div>
</template>

<script setup lang="ts">
let address = ref("Welcome");

import("mainnet-js").then(({ TestNetWallet }) => {
  TestNetWallet.newRandom().then((wallet) => {
    address.value = wallet.address || "No address";
  });
})

</script>
