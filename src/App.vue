<template>
  <!-- <Autentification :isAuth="isAuthentificated"/> -->
  <!-- <UserList /> -->
  <MortgageCalculator />
</template>

<script>
import MortgageCalculator from './components/MortgageCalculator.vue';
import UserList from './components/UserList.vue';
import Autentification from './components/autentification.vue';
export default {
  name: 'App',
  components: {
    Autentification,
    UserList,
    MortgageCalculator
  },
  data() {
    return {
      isAuthentificated: false,
    }
  }
}
</script>

<style lang="scss">
</style>
