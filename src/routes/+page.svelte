<script lang="ts">
  import Window from "$lib/components/Window.svelte";
  import Prog from "$lib/components/Prog.svelte";

  let clicked: HTMLElement | null = $state(null);

  function clickHandler(event: MouseEvent) {
    function toggle(el: HTMLElement) {
      let caption = el.getElementsByTagName("figcaption")[0].classList;
      caption.toggle("text-white");
      caption.toggle("bg-[#000080]");
      caption.toggle("border-dotted");
      caption.toggle("border-1");
      caption.toggle("border-[#ffff00]");

      let mask = document.getElementById("mask");
      if (mask !== null) mask.remove();

      let imgWrapper = el.querySelector(".relative") as HTMLElement;
      let maskEl = document.createElement("div");
      maskEl.classList.add(
        "absolute",
        "inset-0",
        "bg-[image:repeating-conic-gradient(rgba(0,0,128,0.8)_0%_25%,transparent_0%_50%)]",
        "bg-[size:2px_2px]",
        "pointer-events-none",
      );
      maskEl.id = "mask";
      maskEl.style.maskImage = `url(${el.getElementsByTagName("img")[0].src})`;
      maskEl.style.maskSize = "40px 40px";
      imgWrapper.append(maskEl);
    }

    event.stopPropagation();
    const target = event.currentTarget as HTMLElement;

    if (target === clicked) return;
    if (clicked != null) toggle(clicked);
    if (event.currentTarget === window) {
      document.getElementById("mask")?.remove();
      clicked = null;
      return;
    }

    toggle(target);
    clicked = target;
  }

  function dblClickHandler(event: MouseEvent) {
    event.stopPropagation();
    const target = event.currentTarget as HTMLElement;
    alert(`You double-clicked on ${target.innerText}`);
  }
</script>

<svelte:window on:click={clickHandler} />

<Window title="Dent">
  <Prog
    onClick={clickHandler}
    onDblClick={dblClickHandler}
    name="About Me"
    icon="/icons/w98_help_book_big.ico"
  />
  <Prog
    onClick={clickHandler}
    onDblClick={dblClickHandler}
    name="My Artwork"
    icon="/icons/w98_frame_web.ico"
  />
</Window>
