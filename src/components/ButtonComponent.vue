<template>
  <button>
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'ButtonComponent',
};
</script>

<style scoped>
button {
  padding: 10px 20px;
  font-size: 16px;
  background-color: #3498db;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: all 0.3s ease;
  margin: 0rem 1rem;
}

button:hover {
  background-color: #2980b9;
  transform: translateY(-3px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}
</style>
