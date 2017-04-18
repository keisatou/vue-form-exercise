<template>
  <div class="container">
    <form v-if="!isSubmitted">
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <!-- Exercise 1 -->
          <!-- Create a Signup Form where you retrieve the following Information -->
          <!-- Full Name (First Name + Last Name) -->
          <!-- Mail -->
          <!-- Password -->
          <!-- Store Data? Yes/No -->

          <!-- Exercise 2 -->
          <!-- Only display the Form if it has NOT been submitted -->
          <!-- Display the Data Summary ONCE the Form HAS been submitted -->

          <!-- Exercise 3 -->
          <!-- Edit the Example from above and create a custom "Full Name" Control -->
          <!-- which still holds the First Name and Last Name Input Field -->
          <app-fullname v-model="fullname"></app-fullname>
          <div class="form-group">
            <label for="email">Email</label>
            <input
                   id="email"
                   class="form-control"
                   type="text"
                   v-model="email">
          </div>
          <div class="form-group">
            <label for="password">Password</label>
            <input
                   id="password"
                   class="form-control"
                   type="password"
                   v-model="password">
          </div>
          <div class="form-group">
            <label for="storeyes" class="radio-inline">
              <input
                                  type="radio"
                                  id="storeyes"
                                  value="yes"
                                  v-model="storedata">Yes
            </label>
            <label for="storeno" class="radio-inline">
              <input
                                 type="radio"
                                 id="storeno"
                                 value="no"
                                 v-model="storedata">No
            </label>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <button
             class="btn btn-primary"
             @click.prevent="submitted">Submit</button>
        </div>
      </div>
    </form>
    <hr>
    <div class="row" v-if="isSubmitted">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name: {{ fullname }}</p>
            <p>Mail: {{ email }}</p>
            <p>Password: {{ password }}</p>
            <p>Store in Database?: {{ storedata }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import FullName from './FullName.vue';

export default {
  data() {
    return {
      fullname: '',
      email: '',
      password: '',
      storedata: 'yes',
      isSubmitted: false,
    };
  },
  methods: {
    submitted() {
      this.isSubmitted = true;
    },
  },
  components: {
    'app-fullname': FullName,
  },
};
</script>

<style>
</style>
