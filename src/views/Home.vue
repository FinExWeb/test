<script setup>
import Navbar from '../components/Navbar.vue'
import Ques from '../components/Ques.vue'
</script>

<template>
  <div>
    <Navbar />
    <div class="container my-4">
      <div class="nav-content text-center">
        <h1>developer &#60;&#47;&#62; questions</h1>
        <p>A great opportunity to test your knowledge!</p>
      </div>
      <div class="row my-3 justify-content-between card-ques">
        <Ques />
      </div>
    </div>
  </div>
</template>
<style scoped>
@import url(https://fonts.googleapis.com/css2?family=Fira+Code:wght@100;200;300;400;500;600;700&display=swap);

.nav-content h1 {
  font-family: 'Electrolize', sans-serif;
  text-transform: uppercase;
  font-weight: 900;
  font-size: 3rem;
}

.nav-content p {
  font-family: 'Fira Code', monospace;
  text-transform: uppercase;
  opacity: 0.7;
}

@media screen and (max-width: 650px) {
  .card-ques {
    overflow: auto;
    height: 400px;
  }
}
</style>