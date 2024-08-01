<script>
    import "../app.css";
    import { page } from '$app/stores';
    import {
        Navbar,
        NavBrand,
        NavLi,
        NavUl,
        NavHamburger,
    } from "flowbite-svelte";
    $: activeUrl = $page.url.pathname;
</script>

<Navbar let:hidden let:toggle>
    <NavBrand href="/">
        <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">
            SCSOK Hackathon
        </span>
    </NavBrand>
    <NavHamburger on:click={toggle} />
    <NavUl {activeUrl} {hidden}>
        <NavLi href="/">Main</NavLi>
        <NavLi href="/schedule">Schedule</NavLi>
    </NavUl>
</Navbar>

<main>
    <slot></slot>
</main>

<footer class="bg-gray-900 text-white py-8">
    <div class="container mx-auto text-center">
        <p class="text-sm">
            &copy; 2024 Single Cell & Spatial Omics Korea (SCSOK)
        </p>
    </div>
</footer>

<style>
    :global(body) {
        background-color: #f3f4f6;
    }
</style>