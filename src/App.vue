<template>
  <div>
    <header>
      <ButtonComponent @click="displayTheForm = !displayTheForm">Form</ButtonComponent>
      <ButtonComponent @click="displayAdmins = !displayAdmins">Admins</ButtonComponent>
      <ButtonComponent @click="displayUsers = !displayUsers">Users</ButtonComponent>
      <ButtonComponent @click="toggleDarkMode">DarkMode</ButtonComponent>
    </header>
    <FormComponent :displayTheForm="displayTheForm" :displayAdmins="displayAdmins" :displayUsers="displayUsers" />
  </div>
</template>

<script>
import ButtonComponent from './components/ButtonComponent.vue';
import FormComponent from './components/FormComponent.vue';
export default {
  components: {
    ButtonComponent,
    FormComponent,
  },
  data() {
    return {
      displayTheForm: true,
      displayAdmins: true,
      displayUsers: true,
      isDarkMode:false,
      usersArray: [],
      adminsArray: [],
    };
  },
  methods: {
    toggleDarkMode() {
      this.isDarkMode = !this.isDarkMode;
      document.body.classList.toggle('dark-mode', this.isDarkMode); 
    },
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: center;
}

</style>
