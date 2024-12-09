<script lang="ts">
  import { AppBar } from '@skeletonlabs/skeleton';
	import '../app.postcss';
  import "@skeletonlabs/skeleton"
  import '@fortawesome/fontawesome-free/css/all.min.css'
  import { LightSwitch } from '@skeletonlabs/skeleton';
						
  
</script>

<AppBar gridColumns="grid-cols-2" slotDefault="place-self-center" slotTrail="place-content-end">
  <svelte:fragment slot="lead"> </svelte:fragment>
  <svelte:fragment slot="trail">
    <LightSwitch />
  </svelte:fragment>
</AppBar>
<slot />
