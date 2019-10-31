<template>
<v-row class="d-flex justify-center">
  <v-col cols="8">
  <form>
    <v-text-field
      v-model="name"
      :error-messages="nameErrors"
      :counter="20"
      label="Name"
      required
      @input="$v.name.$touch()"
      @blur="$v.name.$touch()"
    ></v-text-field>
    <v-text-field
      v-model="password"
      :error-messages="passwordErrors"
      label="Password"
      required
      @change="$v.password.$touch()"
      @blur="$v.password.$touch()"
    ></v-text-field>
    <v-btn class="mr-4" @click="submit">submit</v-btn>
  </form>
  </v-col>
</v-row>
</template>

<script>
import { validationMixin } from "vuelidate";
import {
  required,
  maxLength,
  minLength,
} from "vuelidate/lib/validators";

export default {
  mixins: [validationMixin],

  validations: {
    name: { required, minLength: minLength(3), maxLength: maxLength(20) },
    password: { required, minLength: minLength(8) },
  },

  data: () => ({
    name: "",
    password: "",
  }),

  computed: {
    passwordErrors() {
      const errors = [];
      if (!this.$v.password.$dirty) return errors;
      !this.$v.password.minLength &&
        errors.push("Password must be at most 8 characters long");
      !this.$v.password.required && errors.push("Password is required");
      return errors;
    },
    nameErrors() {
      const errors = [];
      if (!this.$v.name.$dirty) return errors;
      !this.$v.name.minLength &&
        errors.push("Name must be at most 3 characters long");
      !this.$v.name.maxLength && errors.push("Name is so long");
      !this.$v.name.required && errors.push("Name is required.");
      return errors;
    }
  },

  methods: {
    submit() {
      this.$v.$touch();
    },
    clear() {
      this.$v.$reset();
      this.name = "";
      this.password = "";
    }
  }
};
</script>

<style scoped>
  li {
    text-decoration: none;
    list-style-type: none;
  }
</style>