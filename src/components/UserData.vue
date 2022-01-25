<template>
  <form>
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model="name" />
    </div>

    <div>
      <label for="age">Age</label>
      <input type="number" id="age" v-model="age" />
    </div>

    <div>
      <button @click.prevent="setUser">Set User</button>
    </div>
  </form>
</template>

<script>
export default {
  emmits: ['set-user'],
  data() {
    return {
      name: '',
      age: null,
    };
  },
  methods: {
    validateUser() {
      // sanitaze the name
      const parsedName = this.name.trim();

      // check if the name is valid
      if (parsedName.length < 3) {
        alert('The name must be at least 3 characters long');
        return false;
      }

      // check if the age si valid
      if (!this.age > 0) {
        alert('Please select a valid age number');
        return false;
      }

      return true;
    },
    setUser() {
      // validate the fields
      const isvalid = this.validateUser();

      if (!isvalid) {
        return;
      }

      this.$emit('set-user', {
        name: this.name.trim(),
        age: this.age,
      });
    },
  },
};
</script>
