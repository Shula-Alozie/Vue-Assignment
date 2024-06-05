<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Profile from './components/Profile.vue'
</script>

<template>
  <header>

    <div class="wrapper">
      <div class="profile">
      <Profile msg="You did it!" />
    </div>
      <div class="profile">
      <nav>
        <RouterLink to="/">Repositories</RouterLink>
        <RouterLink to="/follower">Follower</RouterLink>
        <RouterLink to="/following">Following</RouterLink>
      </nav>
      <RouterView />
    </div>
    </div>
  </header>

  
</template>

<style scoped>
.profile {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 50vw;
}

.wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  .wrapper {
    display: flex;
    flex-direction: row;

  }
  /* header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  } */

  /* .logo {
    margin: 0 2rem 0 0;
  } */

 

  /* nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  } */
}
</style>
