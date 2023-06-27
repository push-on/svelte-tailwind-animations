<script>
  let icons = ["☕", "🍕", "🧁", "🍭", "🍩"]
</script>

<div
  class="w-full min-h-screen flex flex-col bg-gradient-to-b from-indigo-800 via-blue-900 to-blue-950 p-10">
  <div class="">
    <div
      class="group fixed bottom-0 left-1/2 -translate-x-1/2 border-t-2 border-white/30 bg-slate-900/40 backdrop-blur-xl m-10 flex justify-center items-center rounded-2xl max-w-fit" >
        {#each icons as icon}
          <button
            class="w-16 h-16 m-2 rounded-lg flex text-4xl cursor-pointer duration-300 justify-center items-center bg-black/20 hover:scale-110 group-active:h-[50vh]"
            on:click={() => (open = true)}>{icon}
          </button>
        {/each}
    </div>
  </div>
</div>

