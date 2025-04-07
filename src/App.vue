<template>
  <div>
    <header>
      <ButtonComponent @click="displayTheForm = !displayTheForm">Form</ButtonComponent>
      <ButtonComponent @click="displayAdmins = !displayAdmins">Admins</ButtonComponent>
      <ButtonComponent @click="displayUsers = !displayUsers">Users</ButtonComponent>
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
      usersArray: [],
      adminsArray: [],
    };
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: center;
}
</style>
