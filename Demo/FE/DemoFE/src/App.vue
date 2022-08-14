<script setup>
import Test from '../src/components/Test.vue'
import axios from 'axios'
const labelBtn = 'Send Request'
function sendRequest() {
  axios.get('http://localhost:8080/hello').then((res) => {
    console.log(res
    );
  })
}

import { ref, onMounted } from 'vue'

const el = ref()

onMounted(() => {
 console.log("App Conponent");
})


</script>

<template>
  <div ref="el">
    <header>
      <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
      <button @click="sendRequest()">{{ labelBtn }}</button>
      <div class="wrapper">
      </div>
    </header>
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
