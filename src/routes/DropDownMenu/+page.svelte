<script>
  let items = ["Child one", "Child two", "Child three", "Child four"]
  // import { slide } from "svelte/transition"
  // let open = false
</script>

<div class="w-full min-h-screen  bg-slate-950 p-10">
  <div
    class="group block m-auto relative w-80 pl-5 py-4 bg-slate-800 text-white text-2xl rounded-xl">
    <ul
      class="bg-slate-800 p-2 absolute top-14 left-0 right-0 h-0 duration-500 transition-all ease-in-out w-full group-hover:h-56 group-hover:translate-y-0 group-hover:opacity-100 opacity-0 rounded-b-xl">
      {#each items as item}
        <li
          class="hover:bg-slate-700 p-2 rounded-xl opacity-0 group-hover:opacity-100 transition-opacity ease-in">
          {item}
        </li>
      {/each}
    </ul>
    <h1 class="font-serif font-bold">Parent Link</h1>
  </div>
</div>
