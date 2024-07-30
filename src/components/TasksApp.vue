<template>
  <div class="check-tarefa">
    <div>
      <svg
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke-width="1.5"
        stroke="currentColor"
        class="check"
        
        :class="{ checkBusiness: tarefa.checkBusiness , checkPersonal: tarefa.checkPersonal, checkComplete: tarefa.isDone }"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M9 12.75 11.25 15 15 9.75M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z"
        />
      </svg>
    </div>
    <div :class="{ checar: tarefa.isDone }">
      {{ tarefa.name }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    tarefa: {
      type: Object,
      required: true
    },
    checkBusiness: {
      type: Boolean
    },
    checkPersonal: {
      type: Boolean
    }
  },
  data () {
    return {}
  }
}
</script>

<style>
.check {
  width: 25px;
  margin: 0px;
}

.checkBusiness {
  background-color: rgb(209, 17, 216);
  border-radius: 50%;
}

.checkPersonal {
  background-color: rgb(0, 119, 255);
  border-radius: 50%;
}

.checkComplete {
  background-color: rgb(190, 188, 188);
}

.checar {
  text-decoration: line-through;
}

.check-tarefa {
  display: flex;
  align-items: center;
}

.tarefas {
  padding: 5px;
  margin-bottom: 10px;
  min-height: 110px;
}

.lista-tarefas {
  list-style: none;
}

.itemTarefa {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: white;
  border-radius: 10px;
  padding: 10px;
  margin-bottom: 10px;
  margin-left: -5px;
  width: 97%;
}

.displayTarefa {
  display:none
}
</style>
