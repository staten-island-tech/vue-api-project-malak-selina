<template>
  <div id="nav" class="nav">
    <router-link to="/" class="brand">Recipes</router-link>
    <nav>
      <router-link :to="{ name:'event-list'}">List</router-link> |
      <router-link :to="{ name:'event-create'}">Search</router-link> 
    </nav>
  </div>
</template>