<script lang="ts">
  import WindowBar from "./WindowBar.svelte";

  let { title, children } = $props();
</script>

<div
  class="relative top-3 left-3 w-[97vw] h-[97vh]
  bg-[#c0c0c0]
  border-l-2 border-l-[#dfdfdf]
  border-t-2 border-t-[#dfdfdf]
  border-r-2 border-r-[#636363]
  border-b-2 border-b-[#636363]"
>
  <WindowBar {title} />
  <ul class="flex list-none m-0 pr-1 bg-[#c0c0c0]">
    <li class="px-2 py-0.5 text-sm cursor-default">
      <u>F</u>ile
    </li>
    <li class="px-2 py-0.5 text-sm cursor-default">
      <u>E</u>dit
    </li>
    <li class="px-2 py-0.5 text-sm cursor-default">
      <u>V</u>iew
    </li>
    <li class="px-2 py-0.5 text-sm cursor-default">
      <u>G</u>o
    </li>
    <li class="px-2 py-0.5 text-sm cursor-default">
      <u>F</u>avorites
    </li>
    <li class="px-2 py-0.5 text-sm cursor-default">
      <u>H</u>elp
    </li>
  </ul>
  <hr class="mx-1 mb-2 border-0 h-px bg-[#808080] shadow-[0_1px_#dfdfdf]" />
  <div
    class="mx-[0.3vw] w-[96vw] h-[86.5vh] bg-white
    border-l-2 border-l-[#808080]
    border-t-2 border-t-[#808080]
    border-r-2 border-r-[#dfdfdf]
    border-b-2 border-b-[#dfdfdf]
    pl-3 pt-2 flex flex-wrap
    shadow-[inset_1px_1px_#000,inset_-1px_-1px_#fff]"
  >
    {@render children()}
  </div>
</div>
