<!-- ===================
COMPONENT JS - BASIC 
  [TypeScript Written]
=================== -->

<script lang="ts">
  import { browser, dev } from '$app/env';

  import { userBetarenaSettings } from '$lib/store/user-settings';

  // ... page-components
  import OfflineAlert from '$lib/components/_Offline_alert.svelte';
  import SplashScreen from '$lib/components/_Splash_screen.svelte';

  import '../app.css';

  // ... on client-side-rendering;
  if (browser) {

      // ... kickstart the .localStorage();
      userBetarenaSettings.useLocalStorage();

      // ... kickstart offline-badge on info;
      window.addEventListener('offline', toggleOfflineAlert);
      window.addEventListener('online', toggleOfflineAlert);
  }

  // ... HIDE/SHOW offline ALERT BADGE;
  let offlineMode: boolean = false;

  async function toggleOfflineAlert() {
      if (dev) console.debug('-- your connection has changed! --');
      offlineMode = !offlineMode;
  }
</script>

<!-- ===================
  COMPONENT HTML
=================== -->

{#if offlineMode}
  <OfflineAlert />
{/if}

<SplashScreen />

<main class:dark-background={$userBetarenaSettings.theme == 'Dark'}>
  <slot />
</main>

<!-- ===================
	COMPONENT STYLE
=================== -->

<!-- ===================
	COMPONENT STYLE
=================== -->

<style>
	main {
    /* 
    so nothing exceeds the main-page-boundries */
    position: relative;
    z-index: 0;
    margin: 0 auto;
    width: 100%;
    /* overflow: hidden; */
    /* 
    make sure the initial page height is always full-device-height as a minumim */
    /* min-height: 100vh; */
  }
</style>
