<template>

<div id="app">
  <div id = "beforeLogin" v-if="!isAuthentication">
    <h1> WItaj w systemie zapisu na zajecia !!!</h1>
    <h1>Twoj e-mail to: {{ email }}</h1>
    <div v-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>
    <input type="email" v-model="email">
    <button :disabled = "email.length < 10" @click="toogle()">Wchodze</button>

  </div>
  <div v-else>
   <h2>Zalogowany jako {{email}}</h2>
    <button @click = "toogle()"> Wyloguj </button>
  </div>

</div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      email: '',
      isAuthentication: false

    }
  }
,
 methods: {
  alertMyEmail(){
    alert(this.email);
    },
    toogle(){
       this.isAuthentication = !this.isAuthentication;
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}



</style>
