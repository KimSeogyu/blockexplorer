<script>
  import { Search, Button, Dropdown, DropdownItem } from "flowbite-svelte";
  import { SearchOutline, ChevronDownSolid } from "flowbite-svelte-icons";

  const items = [
    {
      label: "Blocks",
      placeholder: "blocknumber",
    },
    {
      label: "Transactions",
      placeholder: "transaction hash",
    },
    // {
    //   label: "DID",
    //   placeholder: "did",
    // },
    // {
    //   label: "SBT",
    //   placeholder: "sbt",
    // },
  ];

  let selectCategory = "Blocks";
  let selectHolder = "blocknumber";
  let formValue = "";
</script>

<form
  class="flex z-[2]"
  method="GET"
  on:input={(e) => {
    formValue = e.target.value;
  }}
>
  <div class="relative">
    <Button
      class="rounded-e-none whitespace-nowrap border border-r-0 border-primary-700 bg-violet-500 border-violet-500"
    >
      {selectCategory}
      <ChevronDownSolid class="w-2.5 h-2.5 ml-2.5" />
    </Button>
    <Dropdown classContainer="w-40 z-1">
      {#each items as { label, placeholder }}
        <DropdownItem
          on:click={() => {
            selectCategory = label;
            selectHolder = placeholder;
          }}
          class={selectCategory === label ? "underline" : ""}
        >
          {label}
        </DropdownItem>
      {/each}
    </Dropdown>
  </div>
  <Search
    size="md"
    class="rounded-none py-2.5 "
    placeholder={selectHolder}
    bind:formValue
  />
  <Button
    type="submit"
    formaction={selectCategory.toLowerCase() + "/" + formValue}
    class="!p-2.5 rounded-s-none bg-violet-500"
  >
    <SearchOutline class="w-5 h-5" />
  </Button>
</form>
