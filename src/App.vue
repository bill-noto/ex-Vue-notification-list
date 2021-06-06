<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <list v-if="noti" v-bind:notificationList="this.noti"/>
</template>

<script>
import list from './components/list';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    list
  },
  data(){
    return {
      noti: {}
    }
  },
  mounted(){
    axios.get('https://api.npoint.io/6cb0a271db3f6d5c033c')
          .then((response) => {
            console.log(response.data.notifications);
            this.noti = response.data.notifications;
          })
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
