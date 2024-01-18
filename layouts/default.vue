<template>
  <div class="min-h-screen grid md:grid-cols-12">
    <div class="md:block hidden col-span-2">
      <Sidebar/>
    </div>
    <main class="col-span-10 px-5">
      <Navbar />
      <slot />
    </main>
  </div>
</template>
