<script>
    import "../app.css";
    import { page } from '$app/stores';
    import {
        Navbar,
        NavBrand,
        NavLi,
        NavUl,
        NavHamburger,
        Dropdown,
        DropdownItem,
    } from "flowbite-svelte";
    import { ChevronDownOutline } from "flowbite-svelte-icons";
    $: activeUrl = $page.url.pathname;
</script>

<Navbar let:hidden let:toggle>
    <NavBrand href="/">
        <img src="/scsok-logo.png" class="me-4 h-16 sm:h-20" alt="SCSOK Logo" />
        <span class="self-center whitespace-nowrap text-xl sm:text-2xl font-extrabold tracking-tight text-gray-800 dark:text-white">
            Hackathon
        </span>
    </NavBrand>
    <NavHamburger on:click={toggle} />
    <NavUl {activeUrl} {hidden}>
        <NavLi href="/hackathon/3">Latest Hackathon</NavLi>
        <NavLi class="cursor-pointer">
            Previous Hackathons<ChevronDownOutline class="w-6 h-6 ms-2 text-primary-800 dark:text-white inline" />
        </NavLi>
        <Dropdown class="w-56 z-20">
            <DropdownItem href="/hackathon/2">2nd Hackathon (Feb 2025)</DropdownItem>
            <DropdownItem href="/hackathon/1">1st Hackathon (Aug 2024)</DropdownItem>
        </Dropdown>
    </NavUl>
</Navbar>

<main>
    <slot></slot>
</main>

<footer class="bg-gray-900 text-white py-8">
    <div class="container mx-auto text-center">
        <p class="text-sm">
            &copy; 2025 Single Cell & Spatial Omics Korea (SCSOK)
        </p>
    </div>
</footer>

<style>
    :global(body) {
        background-color: #f3f4f6;
    }
</style>
