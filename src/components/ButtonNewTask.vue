<template>
  <div>
    <button class="btn-nova-tarefa" type="submit">New task</button>
  </div>
</template>

<script>
export default {
}
</script>

<style>
.btn-nova-tarefa {
  background-color: rgb(0, 119, 255);
  border: none;
  border-radius: 20px;
  padding: 15px;
  width: 140px;
  color: white;
  box-shadow: 0px 10px 20px rgba(0, 119, 255, 0.664);
  position: fixed;
  bottom: 50px;
  right: 25px;
  transition: transform .4s ease;
}

.btn-nova-tarefa:hover {
  transform: scale(1.1);
}
</style>
