<script></script>

<template>
  <form v-on:submit="">
    <label for="Longitude">Longitude: </label>
    <input type="text" id="Longitude" />
    <label for="Latitude">Latitude: </label>
    <input type="text" id="Latitude" />
    <button type="submit">Set</button>
  </form>
</template>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 1rem;
  font-size: 1.2rem;
  color: #fafafa;
  background-color: rgba(255, 255, 255, 0.05);
  padding: 1rem;
  border-radius: 15px;
  border: 2px solid hsla(160, 100%, 37%, 0.2);
}

input {
  margin-bottom: 1rem;
  border-radius: 15px;
  opacity: 0.7;
  padding-left: 8px;
  caret-color: #202020;
}

input:focus {
  outline: none;
  opacity: 1;
}

button {
  padding: 0.5rem 1rem;
  background-color: hsla(160, 100%, 37%, 1);
  color: white;
  border-radius: 15px;
  font-weight: 500;
}

button:hover {
  background-color: hsla(160, 100%, 37%, 0.8);
}
</style>
