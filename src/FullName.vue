<template>
  <div class="form-group">
    <label for="firstname">First Name</label>
    <input
           id="firstname"
           class="form-control"
           type="text"
           v-model="firstname"
           @keyup="fullname()">
    <label for="lastname">Last Name</label>
    <input
           id="lastname"
           class="form-control"
           type="text"
           v-model="lastname"
           @keyup="fullname()">
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstname: '',
      lastname: '',
    };
  },
  methods: {
    fullname() {
      this.$emit('input', `${this.firstname} ${this.lastname}`);
    },
  },
};
</script>

<style>
</style>
