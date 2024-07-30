<template>
  <div>
    <input
      type="text"
      class="nova-tarefa"
      placeholder="Enter new task and choose a category below"
      autocomplete="off"
      @input="(e) => $emit('update:modelValue', e.target.value)"
    />
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: String
    }
  }
}
</script>

<style>
.nova-tarefa {
  border: none;
  padding: 20px;
  font-size: 16px;
  margin: 70px 0px 20px 0px;
  width: 50vw;
  height: 100px;
  border-radius: 10px;
}
</style>
