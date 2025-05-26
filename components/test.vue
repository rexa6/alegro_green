<template>
  <div class="container">
    <button class="inc" @click="increment">
      Click {{ count }}
    </button>

    <button class="inc" v-if="typeuser === 'admin'" @click="showHideUsers">
      {{ showuser ? 'Hide Users' : 'Show Users' }}
    </button>

    <ul v-if="showuser" class="user-list">
      <li>Nigeria</li>
      <li>SUperMan</li>
      <li>TumTumSatur</li>
      <li>Hihahahah</li>
    </ul>

    <input class="input" type="text" placeholder="Enter your name" v-model="name" />
    <p v-if="name">Hello, {{ name }}</p>
  </div>
</template>

<script lang="ts" setup>
const count = ref(0);
const increment = () => {
  count.value++;
};

const name = ref('');
const typeuser = ref('admin');

const showuser = ref(false);
const showHideUsers = () => {
  showuser.value = !showuser.value;
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
  width: 70%;
  margin: 50px auto;
  padding: 20px;
  background-color: #f8f0fb;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.inc {
  padding: 10px 20px;
  border: none;
  border-radius: 6px;
  background-color: #c940c9;
  cursor: pointer;
  color: white;
  font-size: 16px;
  transition: background-color 0.3s ease;
}

.inc:hover {
  background-color: #b134b9;
}

.input {
  padding: 10px;
  width: 100%;
  border: none;
  border-radius: 6px;
  background-color: #e3c5e8;
  color: #333;
  font-size: 16px;
}

.user-list {
  list-style: none;
  padding: 0;
  margin: 0;
  width: 100%;
  text-align: left;
}

.user-list li {
  padding: 6px 0;
  border-bottom: 1px solid #ddd;
  font-size: 15px;
}
</style>
