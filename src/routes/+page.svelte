<script>
  import SearchBar from "../components/SearchBar.svelte";
</script>

<main class="flex flex-col flex-1 p-4">
  <section
    id="introPage"
    class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14"
  >
    <div
      class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10 z-[2]"
    >
      <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
        Find <span class="poppins text-violet-400"
          >Every Information in Blockchain</span
        >
      </h2>
      <SearchBar />
    </div>
  </section>
</main>
