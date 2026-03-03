<script lang="ts">
  import Button from "./Button.svelte";

  let { title } = $props();
</script>

<div
  class="border-solid border-white border
  bg-linear-to-r from-[#000072] to-[#0e7bc1]
  relative flex py-1"
>
  <h1 class="text-white font-bold mx-2 my-auto">{title}</h1>
  <div class="absolute right-0 flex mx-2">
    <Button><i class="fas fa-minus"></i></Button>
    <Button><i class="far fa-square"></i></Button>
    <Button><i class="fas fa-xmark"></i></Button>
  </div>
</div>
