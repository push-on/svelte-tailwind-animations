<script>
  let icons = ["☕", "🍕", "🧁", "🍭", "🍩"]
  import { slide } from "svelte/transition"
  let open = false
</script>

<div
  class="w-full min-h-screen flex flex-col bg-gradient-to-b from-sky-800 via-blue-900 to-blue-950 p-10">
  <div class="">
    <div class="overflow-hidden">
      <p class="italic font-serif SlideDown delay-500">
        <a
          class="duration-200 text-2xl underline underline-offset-4 text-slate-300 hover:text-slate-50 decoration-sky-500"
          href="/">Home</a>
      </p>
    </div>
    {#key open}
      <div
        in:slide 
        out:slide 
        class="fixed bottom-0 left-1/2 -translate-x-1/2 border-t-2 border-white/30 bg-slate-900/40 backdrop-blur-xl m-10 flex justify-center items-center rounded-2xl max-w-fit {open
          ? 'h-2/4'
          : ''}">
        {#if open}
          <div class="space-y-3 font-serif p-4">
            <h1 class="text-2xl md:text-5xl sm:text-3xl italic font-bold">
              This is the dock content
            </h1>
            <p class="text-lg md:text-2xl sm:text-xl text-gray-200">
              You can put anything here
            </p>
            <button
              class="bg-black/20 text-indigo-200 hover:text-indigo-50 text-lg md:text-2xl px-6 py-2 rounded-full uppercase font-sans font-medium"
              on:click={() => (open = false)}>Close</button>
          </div>
        {:else}
          {#each icons as icon}
            <button
              class="w-16 h-16 m-2 rounded-lg flex text-4xl cursor-pointer duration-300 justify-center items-center bg-black/20 hover:scale-110"
              on:click={() => (open = true)}>{icon}</button>
          {/each}
        {/if}
      </div>
    {/key}
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
