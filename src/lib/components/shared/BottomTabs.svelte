<script lang="ts">
    import { routes, type Icon as Icons } from '$lib/commons/data';
    import ActiveLink from './ActiveLink.svelte';
    import Icon from './Icon.svelte';

    class Tab {
        constructor(
            public name: string,
            public to: string,
            public icon: keyof Icons
        ) {}
    }

    const tabs = [
        new Tab('Home', routes.home, 'home'),
        new Tab('Live', routes.sports_live, 'users'),
        new Tab('Play', routes.sports_live, 'play'),
        new Tab('Profile', routes.profile, 'user'),
    ];
</script>

<nav
    class="z-1 fixed bottom-0 left-0 right-0 flex items-center justify-evenly py-2 px-4 bottom-tabs-bg sm:hidden"
>
    {#each tabs as tab}
        <ActiveLink to={tab.to} className="flex flex-col items-center" >
            <Icon name={tab.icon} className="text-3xl text-gray-300" />
            <span class="text-xs text-gray-300">{tab.name}</span>
        </ActiveLink>
    {/each}
</nav>

<style>
    .bottom-tabs-bg {
        @apply bg-[#10181c] bg-clip-padding backdrop-filter backdrop-blur-sm bg-opacity-[0.95];
    }
</style>
