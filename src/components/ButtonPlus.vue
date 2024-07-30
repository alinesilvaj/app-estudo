<template>
    <div>
      <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          fill="currentColor"
          class="btnAdicionar"
        >
          <path
            fill-rule="evenodd"
            d="M12 2.25c-5.385 0-9.75 4.365-9.75 9.75s4.365 9.75 9.75 9.75 9.75-4.365 9.75-9.75S17.385 2.25 12 2.25ZM12.75 9a.75.75 0 0 0-1.5 0v2.25H9a.75.75 0 0 0 0 1.5h2.25V15a.75.75 0 0 0 1.5 0v-2.25H15a.75.75 0 0 0 0-1.5h-2.25V9Z"
            clip-rule="evenodd"
          />
        </svg>
    </div>
</template>

<script>
</script>

<style>
.btnAdicionar {
  width: 60px;
  position: fixed;
  bottom: 50px;
  right: 25px;
  transition: transform .6s ease;
}

.btnAdicionar:hover {
  transform: scale(1.2);
}
</style>