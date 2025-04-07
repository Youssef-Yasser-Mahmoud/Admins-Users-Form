<template>
  <form @submit.prevent="handleSubmit">
    <label>
      Enter Your Name
      <input required v-model="formData.personName" type="text" name="name" placeholder="userName" />
    </label>

    <label>
      Enter Your Age
      <input required v-model="formData.personAge" type="number" name="age" placeholder="age" />
    </label>

    <label>
      User
      <input required v-model="formData.role" type="radio" name="role" value="user" />
    </label>
    <label>
      Admin
      <input required v-model="formData.role" type="radio" name="role" value="admin" />
    </label>

    <ButtonComponent type="submit">Submit</ButtonComponent>
  </form>
</template>

<script>
import ButtonComponent from './ButtonComponent.vue';
export default {
  name: 'FormComponent',
  components: { ButtonComponent },
  data() {
    return {
      formData: {
        personName: '',
        personAge: '',
        role: '',
      },
      users: [],
      admins: []
    };
  },
  methods: {
    handleSubmit() {
      if (this.formData.role === 'user') {
        // If role is 'user', push data into users array
        this.users.push({
          id: Math.random(),
          name: this.formData.personName,
          age: this.formData.personAge,
        });
      } else if (this.formData.role === 'admin') {
        // If role is 'admin', push data into admins array
        this.admins.push({
          id: Math.random(),
          name: this.formData.personName,
          age: this.formData.personAge,
        });
      }

      this.formData.personName = '';
      this.formData.personAge = '';
      this.formData.role = '';

      console.log(this.users);
      console.log(this.admins);
    },
  },
};
</script>

<style scoped>
form {
  width: 300px;
  margin: 20px auto;
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

label {
  display: block;
  margin-bottom: 10px;
  font-size: 14px;
  font-weight: bold;
}

input[type='text'],
input[type='number'] {
  width: 100%;
  padding: 8px;
  margin-top: 5px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type='radio'] {
  margin-left: 5px;
}

input[type='radio']:not(:last-child) {
  margin-right: 10px;
}

button {
  width: 100%;
}
</style>
