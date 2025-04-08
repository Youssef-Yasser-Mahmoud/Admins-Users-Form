<template>
  <div v-show="displayUsers">
    <table class="user-table">
      <caption class="table-caption">
        Users
      </caption>
      <thead>
        <tr>
          <th>Name</th>
          <th>Age</th>
          <th>Actions</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id">
          <td>{{ user.name }}</td>
          <td>{{ user.age }}</td>
          <td><button class="delete-btn" @click="$emit('delete-user', user.id)">Delete User</button></td>
        </tr>
      </tbody>
      <tfoot>
        <tr>
          <td colspan="3" class="clear-all">
            <button v-show="users.length" class="delete-btn" @click="$emit('clearAllUser')">Clear All</button>
          </td>
        </tr>
      </tfoot>
    </table>
  </div>
</template>

<script>
export default {
  name: 'UsersComponent',
  props: ['displayUsers', 'users'],
};
</script>

<style scoped>
.user-table {
  width: 100%;
  border-collapse: collapse;
  margin: 20px 0;
  font-family: Arial, sans-serif;
  background-color: #f8f9fa;
}

.user-table th,
.user-table td {
  padding: 12px 15px;
  text-align: left;
  border-bottom: 1px solid #ddd;
}

.user-table th {
  background-color: #007bff;
  color: white;
  font-weight: bold;
}

.user-table tbody tr:hover {
  background-color: #f1f1f1;
}

.clear-all {
  text-align: center;
  padding: 10px 0;
}

.clear-all button {
  width: 40%;
  padding: 10px;
}
.table-caption {
  font-size: 1.5rem;
  font-weight: bold;
  color: #007bff;
  text-align: center;
  background-color: #f1f1f1;
  padding: 10px;
  border-top: 2px solid #007bff;
  border-bottom: 2px solid #007bff;
}

.delete-btn {
  background-color: #dc3545;
  color: white;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
  border-radius: 4px;
  font-size: 14px;
  transition: background-color 0.3s ease;
}

.delete-btn:hover {
  background-color: #c82333;
}

.delete-btn:focus {
  outline: none;
}

@media (max-width: 600px) {
  .user-table th,
  .user-table td {
    padding: 8px;
  }

  .delete-btn {
    padding: 4px 8px;
    font-size: 12px;
  }
}
</style>
