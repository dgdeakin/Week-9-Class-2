<template>
  <div>
    <h1>This is an about page</h1>
    <h2>{{ $route.params.id }}</h2>

    <h2>{{ $route.params.postid }}</h2>

    <button
      @click="
        {
          router.push('/');
        }
      "
    >
      Back to HomePage
    </button>

    <button @click="goToHomePage">Back to HomePage With Method</button>
    <button @click="router.go(-2)">Back To few steps</button>
    <button @click="router.go(2)">Foward to few steps</button>
    <br />
    <RouterLink :to="{ name: 'about', params: { id: 70000 } }"
      >Using RouterLink</RouterLink
    >

    <br />
    <button @click="router.push('/about/400/children')">
      Show children view page also
    </button>

    <button @click="router.push('/routers')">To Multiple RouterView</button>
  </div>
  <RouterView />
</template>

<script setup>
import router from "../router";
import { RouterView, RouterLink } from "vue-router";

const value = 5000;

function goToHomePage() {
  router.push("/");
}
</script>

<style scoped>
div {
  border: 5px outset red;
  background-color: lightblue;
  text-align: center;
  height: 300px;
}

@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
