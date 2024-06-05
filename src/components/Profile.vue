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
        <img alt="Vue logo" class="logo" src="@/assets/Mypix.jpg" width="300" height="300" />
        <h1 class="h1">{{ user.name }}</h1>
        <h3 class="h3">{{ user.login }}</h3>
        <p class="profile"><span> Followers:</span>{{ user.followers }}</p>
        <p class="profile"><span>Following:</span>{{ user.following  }}</p>
        <p class="profile"><span>Public_repos:</span>{{ user.public_repos }}</p>
        
        <button  class="button">
            <a href="https://github.com/settings/profile">Get Repo</a>
        </button>
    </div>

  </template>
  <style>
  .h1{
    font-size: 20px;
    font-weight: 500;
    padding-left: 10%;
  }

  .logo{
    border-radius:50%;
    margin-top: 8% 
  }

.h3{
    font-size: 15px;
    padding-left: 10%;
    font-weight: 400;
}

/* .repo{
    display: flex;
    flex-direction: row;
    border: 1px;
    border-color: brown; */
/* } */

.button{
    color: black;
    padding: 14px 100px;
    border-radius: 20%;
    border: 0;
    background-color: grey;
    margin-left: 20px;
    margin-top: 20px;
}

.profile{
    padding-left: 70px;
}
.profile span{
    margin-right: 5px;
    /* padding-right: ; */
}
</style>