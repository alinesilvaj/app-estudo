<template>
  <div>
    <input
      type="text"
      class="navInput"
      placeholder="Search task"
      @input="(e) => $emit('update:modelValue', e.target.value)"
    />
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: String
    },
    searchBar: {
      type: Boolean
    },
  },
}
</script>

<style>
.pesquisa {
  display: flex;
  align-items: center;
}
.navInput {
  padding: 10px;
  width: 25vw;
  border-radius: 5px;
  border: 1px solid rgb(97, 97, 97);
}
</style>
