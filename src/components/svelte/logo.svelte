<script lang="ts">
import { logoSpelling } from "~/content/common.ts";
import { useStore } from "~/hooks/core.svelte";
import { isMenuOpenStore } from "~/stores/menu";

const { class: className, id }: { class?: string; id?: string } = $props();

const isMenuOpen = useStore(isMenuOpenStore);
</script>

<a {id} class={`${className} tracking-widest`} href="/" onclick={() => {
  isMenuOpen.value = false
}}>
  {#each logoSpelling.split("") as letter}
    <span>
      {letter}
    </span>
  {/each}
  <span class="font-bold text-[1em] text-[#fe4164]">
    .
  </span>
</a>
