<template>
  <option>{{ options.text }}</option>
</template>

<script>
export default {
  props: {
    options: {
      type: Object,
      required: true
    }
  }
}
</script>

<style>
.select {
    display: none;
  padding: 9px;
  width: 170px;
  border-radius: 5px;
  border: 1px solid rgb(97, 97, 97);
}
</style>
