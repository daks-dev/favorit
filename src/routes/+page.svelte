<script lang="ts">
  import { onMount } from 'svelte';
  import { fly, fade } from 'svelte/transition';
  import { confetti } from '@neoconfetti/svelte';
  import { YandexMetrikaHit, Icon } from 'daks-svelte';

  const size = '100%';
  const year = new Date().getFullYear();

  const title = 'СК «Фаворит» • Строительный контроль в Москве';
  const description =
    'Строительство и ремонт зданий, строительный контроль и технический надзор в Москве. Строительное Управление № 363';

  let visible = false;
  onMount(() =>
    setTimeout(() => {
      visible = true;
    }, 1555)
  );
</script>

<YandexMetrikaHit
  {title}
  {description} />

<main
  class="justify-center items-center text-center grow overflow-hidden"
  itemprop="mainContentOfPage">
  <div
    use:confetti={{
      force: 0.77,
      duration: 5555,
      destroyAfterDone: true
    }}
    aria-hidden="true" />
  <h1 class="mb-4 text-2xl md:text-3xl lg:text-4xl xl:text-7xl text-slate-500">
    Строительный &ndash; Контроль • Москва
  </h1>
  <div class="relative h-[35vmin] aspect-square text-slate-700 dark:text-slate-400">
    {#if visible}
      <div
        in:fly={{ y: -500, delay: 1500, duration: 1500 }}
        class="absolute top-0 left-0 h-inherit aspect-square">
        <Icon
          icon="emojione-monotone:construction"
          rel="image"
          class="py-8 opacity-75 hover:scale-125 duration-500"
          width={size}
          height={size} />
      </div>
    {:else}
      <div
        out:fade={{ duration: 3000 }}
        class="absolute top-0 left-0 h-inherit  aspect-square">
        <Icon
          icon="emojione-monotone:construction-worker"
          rel="image"
          class="py-8 opacity-75"
          width={size}
          height={size} />
      </div>
    {/if}
  </div>
  <h3 class="mb-8 whitespace-nowrap text-3xl text-slate-500">
    Строительная Компания «Фаворит»
  </h3>
  <a
    rel="noreferrer nofollow"
    class="button whitespace-nowrap hover:text-gray-100 hover:bg-slate-500"
    href="https://kit.svelte.dev"
    target="_blank">
    {year} &star; Svelte.Kit
  </a>
</main>
