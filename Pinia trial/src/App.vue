<script setup>
import { RouterLink,RouterView} from 'vue-router'
import TodoList from './components/TodoList.vue';
</script>

<template>
  <header>
    <div class="router">
      <nav>
        <h1>TodoApp</h1>
      <div class="bar">
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/Todos">Todos </RouterLink>
      </div>
      </nav>
    </div>  
  </header>
  <RouterView />
  <TodoList />
</template>

<style scoped>
header{
  display: flex;
  justify-content: center;
  padding-top: 27px;
  border-radius: 8px;
  height: 63px;
}
.router{
  color: black;
  padding: 40px;
  background-color: whitesmoke;
  width: 800px;
  
}
 h1{
color: #000;
font-family: Inter;
font-size: 16px;
font-style: normal;
font-weight: 600;
line-height: normal;
gap: 370px;
align-items: center;
 }

nav{
  display: flex;
  gap: 300px;
}
a{
  text-decoration: none;
}
.bar{
  gap: 50px;
  justify-content: space-between;
  display: flex;
  padding-right: 27px;
}
</style>
