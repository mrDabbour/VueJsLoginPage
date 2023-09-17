<template>
  <div class="form-labels">
    <label class="form-label" for="username">Username</label>

    <div class="form-error">error</div>
  </div>
  <input class="form-input" type="text" id="username" />
</template>

<style scoped>
.form-labels {
  display: flex;
  justify-content: space-between;
}

.form-error {
  color: tomato;
    cursor: pointer;
}

.form-input {
  outline: none;
  border: none;
  background: white;
  color: #000;
  padding: 0.7rem;
  margin: 1rem 0;
  border-radius: 8px;
}
</style>
