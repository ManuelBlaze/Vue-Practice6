<template>
  <section>
    <header>
      <h1>Vue Practice #6 (Components)</h1>
    </header>

    <section>
      <user-data @set-user="setUser" />
    </section>

    <p v-if="!isUser"><strong> Add the user info! </strong></p>
  </section>
</template>

<script>
import UserData from './components/UserData.vue';

export default {
  components: { UserData },
  data() {
    return { user: {} };
  },
  computed: {
    isUser() {
      return !Object.keys(this.user).length === 0;
    },
  },
  methods: {
    setUser(user) {
      this.user = user;
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Jost&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Jost', sans-serif;
}

body {
  margin: 0;
}

header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #34495e;
  color: white;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

p {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

#app button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #41b883;
  background-color: #41b883;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
  margin: 0 6px;
}

#app button:hover,
#app button:active {
  background-color: #41a779;
  border-color: #41a779;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}

#app input {
  font: inherit;
  padding: 0.15rem;
}
#app label {
  font-weight: bold;
  margin-right: 1rem;
  width: 7rem;
  display: inline-block;
}
#app form div {
  margin: 1rem 0;
}

#app ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

#app li,
#app form {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

#app h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #34495e;
  margin: 0 0 1rem 0;
}
</style>
