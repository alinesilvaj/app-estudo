<template>
  <div class="categoria">
    <div class="quantidade-categoria"><p>tasks: {{ title }}</p></div>
    <div><p>{{ subTitle }}</p></div>
    <div class="barra-cinza">
      <div
      :class="{ 'barra-business': barraBusiness, 'barra-personal': barraPersonal}"
      :style="{ width: progress + '%' }">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: Number,
      required: true
    },
    subTitle: {
      type: String,
      required: true
    },
    progress: {
      type: Number,
      required: true
    },
    barraBusiness: {
      type: Boolean
    },
    barraPersonal: {
      type: Boolean
    }
  },
  data() {
    return {
      
    }
  }
}
</script>

<style>
.tipos-categorias {
  overflow: auto;
  position: relative;
  display: flex;
}

.categoria {
  background-color: white;
  margin: 0px 10px 10px 0px;
  border-radius: 10px;
  min-width: 200px;
  padding: 10px 0px 10px 10px;
}

.quantidade-categoria {
  color: grey;
  font-weight: bold;
  font-size: 12px;
}

.categoria > div > p {
  font-weight: bold;
}

.barra-cinza {
  max-width: 170px;
  height: 5px;
  background-color: lightgrey;
}

.barra-business,
.barra-personal {
  position: relative;
  height: 5px;
  left: -5px;
  float: left;
}

.barra-business {
  background-color: rgb(209, 17, 216);
}

.barra-personal {
  background-color: rgb(0, 119, 255);
}

.categorias {
  padding: 5px;
  margin-bottom: 10px;
}
</style>
