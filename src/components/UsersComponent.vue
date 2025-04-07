<template>
  <div v-show="displayUsers">
    <table class="user-table">
      <thead>
        <tr>
          <th>Name</th>
          <th>Age</th>
          <th>Actions</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>John Doe</td>
          <td>28</td>
          <td><button class="delete-btn">Delete User</button></td>
        </tr>
        <tr>
          <td>Jane Smith</td>
          <td>34</td>
          <td><button class="delete-btn">Delete User</button></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'UsersComponent',
  props: ['displayUsers'],
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
