<script lang="ts">
  import '../app.css';
  import '../i18n';

  import { onDestroy, onMount } from 'svelte';

  import { Header } from '$components/Header';
  import { SideNavigation } from '$components/SideNavigation';
  import { startWatching, stopWatching } from '$libs/wagmi';

  onMount(startWatching);
  onDestroy(stopWatching);
</script>

<SideNavigation>
  <Header />
  <main class="my-8 md:my-14">
    <slot />
  </main>
</SideNavigation>
