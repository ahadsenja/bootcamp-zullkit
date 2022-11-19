<template>
  <div class="flex items-center md:order-2">
    <div class="mr-2 text-sm font-regular">Halo, Daniel</div>
    <button
      class="flex mr-3 text-sm bg-gray-800 rounded-full md:mr-0 focus:ring-4 focus:ring-gray-300 dark:focus:ring-gray-600"
      type="button"
      id="user-menu-button"
      aria-expanded="false"
      data-dropdown-toggle="drowpdown"
    >
      <span class="sr-only">Open user menu</span>
      <img
        class="w-8 h-8 rounded-full"
        src="https://ui-avatars.com/api/?name=Galih+Pratama&background=160442&color=fff"
        alt="User photo"
      />
    </button>
    <div
      class="z-50 hidden my-4 text-base list-none bg-white divide-y divide-gray-100 rounded shadow dark:bg-gray-700 dark:divide-gray-600"
      id="dropdown"
    ></div>
  </div>
</template>
