<template>
  <div class="escolhaCategoria">
    <input
      type="radio"
      name="category"
      id="taskBusiness"
      @input="() => $emit('update:modelValue', 'Business')"
      > 
    <label for="taskBusiness">Business</label>

    <input
      type="radio"
      name="category"
      id="taskPersonal"
      @input="() => $emit('update:modelValue', 'Personal')"
      >
    <label for="taskPersonal">Personal</label>
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
.escolhaCategoria {
  font-size: 15px;
  margin-bottom: 0px
}
</style>
