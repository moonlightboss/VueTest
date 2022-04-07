<template>
  <regiser-user @add-person="newPerson" />
  <div v-for="p in register" v-bind:key="p">
    {{ p.name }} {{ p.phonenumber }} {{ p.email }} {{ p.passwrd }}
  </div>
  <div>{{ register.name }}</div>
</template>

<script>
import RegiserUser from "@/components/RegisterUser.vue";
export default {
  methods: {},
  components: {
    RegiserUser,
  },
  name: "App",
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
  props: {
    regdata: {
      type: Array,
      require: true,
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
