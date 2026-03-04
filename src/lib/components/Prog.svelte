<script lang="ts">
  let { icon, name } = $props();
</script>

<figure class="flex flex-col items-center w-18 cursor-default select-none mt-2">
  <img src={icon} width="40" height="40" alt={name} class="mb-1" />
  <figcaption class="text-xs text-center wrap-break-word leading-tight">
    {name}
  </figcaption>
</figure>
