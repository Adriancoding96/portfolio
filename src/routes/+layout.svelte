<script lang="ts">
  import { AppBar } from '@skeletonlabs/skeleton';
	import '../app.postcss';
  import "@skeletonlabs/skeleton"
  import '@fortawesome/fontawesome-free/css/all.min.css'
  import { LightSwitch } from '@skeletonlabs/skeleton';
  import { currentTheme } from "$lib/store";
  import { browser } from "$app/environment";
  
  const availableThemes: String[] = [
    "skeleton",
    "wintry",
    "modern",
    "rocket",
    "seafoam",
    "vintage",
    "sahara",
    "hamlindigo",
    "goldnouveau",
    "crimson",
  ];

  $: if (browser) {
    document.body.setAttribute("data-theme", $currentTheme);
  }

  function handleThemeChange(event: Event) {
    const select = event.target as HTMLSelectElement;
    currentTheme.set(select.value);
  }

</script>

<AppBar gridColumns=" grid-cols-2" slotDefault="place-self-center" slotTrail="place-content-end">
  <svelte:fragment slot="lead"> 
  </svelte:fragment>
  <svelte:fragment slot="trail">
    <div class="space-x-6 flex">
      <select on:change={handleThemeChange} class="select h-8 mt-3">
        {#each availableThemes as theme}
          <option value={theme} selected={theme === $currentTheme}>{theme}</option> 
        {/each}
      </select>
      <div class="p-4">
         <LightSwitch  />
      </div>
    </div>
  </svelte:fragment>
</AppBar>
<slot />

