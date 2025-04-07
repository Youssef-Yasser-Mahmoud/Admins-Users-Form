<template>
  <div>
    <header>
      <ButtonComponent @click="displayTheForm = !displayTheForm">Form</ButtonComponent>
      <ButtonComponent>Admins</ButtonComponent>
      <ButtonComponent>Users</ButtonComponent>
    </header>
    <FormComponent v-show="displayTheForm" />
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
