<script>
  let items = ["Child one", "Child two", "Child three", "Child four"]
  // import { slide } from "svelte/transition"
  // let open = false
</script>

<div
  class="w-full min-h-screen flex flex-col items-center bg-slate-950 p-10 space-y-10">
  <div class="overflow-hidden">
    <p class="italic font-serif SlideDown delay-500">
      <a
        class="duration-200 text-2xl underline underline-offset-4 text-slate-300 hover:text-slate-50 decoration-sky-500"
        href="/">Home</a>
    </p>
  </div>
  <div
    class="group block relative w-80 pl-5 py-4 bg-slate-800 text-white text-2xl rounded-xl cursor-pointer no_tap_highlights">
    <ul
      class="bg-slate-800 p-2 absolute top-14 left-0 right-0 h-0 duration-500 transition-all ease-in-out w-full group-hover:h-56 group-hover:translate-y-0 group-hover:opacity-100 opacity-0 rounded-b-xl">
      {#each items as item}
        <li
          class="hover:bg-slate-700 p-2 text-slate-400 hover:text-slate-50 rounded-xl opacity-0 group-hover:opacity-100 transition-all ease-in">
          {item}
        </li>
      {/each}
    </ul>
    <h1
      class="font-serif font-bold underline decoration-transparent transition-all ease-in duration-300 group-hover:decoration-slate-400 decoration-2 underline-offset-8">
      Parent Link
    </h1>
  </div>
</div>

<style>
  .SlideDown {
    animation-delay: 400ms;
    transform: translateY(-100%);
    animation-name: slideDown;
    animation-duration: 1.7s;
    animation-timing-function: cubic-bezier(0.165, 0.84, 0.44, 1);
    animation-fill-mode: forwards;
  }

  @keyframes slideDown {
    to {
      transform: translate(0);
    }
  }
</style>
