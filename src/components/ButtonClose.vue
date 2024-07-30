<template>
        <div>
      <svg
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        strokeWidth="{1.5}"
        stroke="currentColor"
        class="btn-fechar"
      >
        <path
          strokeLinecap="round"
          strokeLinejoin="round"
          d="m9.75 9.75 4.5 4.5m0-4.5-4.5 4.5M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z"
        />
      </svg>
    </div>
</template>

<script>
</script>

<style>
.btn-fechar {
  width: 40px;
  float: right;
  margin-top: 10px;
  margin-right: 25px;
  transition: transform .4s ease;
}

.btn-fechar:hover {
 transform: scale(1.1);
}
</style>