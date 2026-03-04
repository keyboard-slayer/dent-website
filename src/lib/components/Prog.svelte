<script lang="ts">
  let { icon, name, onClick, onDblClick } = $props();
</script>

<!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
<!-- svelte-ignore a11y_click_events_have_key_events -->
<figure
  class="flex flex-col items-center w-18 h-17 cursor-default select-none mt-2"
  onclick={onClick}
  ondblclick={onDblClick}
>
  <div class="relative mb-1">
    <img src={icon} width="40" height="40" alt={name} />
  </div>
  <figcaption class="text-xs text-center wrap-break-word leading-tight">
    {name}
  </figcaption>
</figure>
