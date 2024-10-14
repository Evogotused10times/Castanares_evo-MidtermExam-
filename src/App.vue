<template>
  <div>
    <nav>
      <router-link to="/home">Home</router-link>
      <router-link to="/products">Products</router-link>
    </nav>
    <router-view />
  </div>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style scoped>
nav {
  background-color: #8d8d8d;
  border-radius: 8px;
  padding: 10px;
}

router-link {
  border-radius: 8px;
  display: flex;
  gap: 10px;
  margin-right: 10px;
}

router-link:hover {
  background-color: aquamarine;
}
</style>
