<template>
  <header>
    <h1 class="logo">
      <router-link to="/">
        <span v-if="userMenu">{{userMenu.storeName}}</span>
        <span v-if="!userMenu">Your Menu</span>
      </router-link>
    </h1>
    <Navigation v-if="userMenu" v-bind:userMenu="userMenu"/>
    <SignInSignOut
      v-bind:isConnected="isConnected"
      v-bind:currentUser="currentUser"
    />
  </header>
</template>

<style lang="scss" scoped>
header {
  display: flex;
  align-items: center;
  padding: 10px 30px;
  background: #eee;
  h1 {
    margin: 0 30px 0 0;
    a {
      text-decoration: none;
      color: #000;
    }
  }
}
</style>

<script>
import Navigation from '@/components/Navigation.vue';
import SignInSignOut from '@/components/SignInSignOut.vue';

export default {
  name: 'site-header',
  components: {
    Navigation,
    SignInSignOut,
  },
  props: ['isConnected', 'currentUser', 'userMenu'],
};
</script>
