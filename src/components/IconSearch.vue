<template>
    <div>
      <button class="nav-search" title="Search task">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            strokeWidth="{1.5}"
            stroke="currentColor"
            class="menu-icon "
          >
            <path
              strokeLinecap="round"
              strokeLinejoin="round"
              d="m21 21-5.197-5.197m0 0A7.5 7.5 0 1 0 5.196 5.196a7.5 7.5 0 0 0 10.607 10.607Z"
            />
          </svg>
      </button>
    </div>
</template>

<script></script>

<style>
.nav-search {
  display: none;
  margin-right: 15px;
  background-color: white;
  border-radius: 5px;
  border: 1px solid rgb(97, 97, 97);
  transition: transform .2s ease;
}
.nav-search:hover {
  transform: scale(1.03);
}
</style>
