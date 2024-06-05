<script>
export default {
  data() {
    return {
      user: null,
    };
  },
  created() {
    this.fetchUserData();
  },
  methods: {
    async fetchUserData() {
      try {
        const response = await fetch('https://api.github.com/users/shula-alozie');
        const data = await response.json();
        this.user = data;
      } catch (error) {
        console.error('Error fetching user data:', error);
      }
    },
  },
};
</script>
<template>
    <div>
        <h1>Popular Repositories</h1>
        <h2>
            shulizconcept.github.io
            <a href=""></a>
        </h2>
    </div>
       
    
</template>
<style>

</style>