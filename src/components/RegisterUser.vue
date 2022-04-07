<template>
  <div id="app">
    <form @submit.prevent>
      <h3>Register</h3>
      <input
        class="floatLabel"
        v-model="register.name"
        type="text"
        placeholder="Name"
      />
      <input
        class="floatLabel"
        v-model="register.phonenumber"
        type="text"
        placeholder="PhoneNumber"
      />
      <input
        class="floatLabel"
        v-model="register.email"
        type="text"
        placeholder="E-mail"
      />
      <input
        class="floatLabel"
        v-model="register.passwrd"
        type="text"
        placeholder="Pass"
      />
      <submit-button @click="addPerson" />
    </form>
  </div>
</template>

<script>
import SubmitButton from "@/components/SubmitButton.vue";
export default {
  data() {
    return {
      register: [
        {
          name: "default",
          phonenumber: "defaultphone",
          email: "defaultemail",
          passwrd: "defaultpw",
        },
      ],
    };
  },
  components: {
    SubmitButton,
  },
  methods: {
    addPerson() {
      const newPerson = {
        name: this.register.name,
        phonenumber: this.register.phonenumber,
        email: this.register.email,
        passwrd: this.register.passwrd,
      };
      this.register.push(newPerson);
      console.log(newPerson);
      this.$emit("add-person", this.newPerson);
      this.newPerson;
    },
  },
};
</script>

<style></style>
