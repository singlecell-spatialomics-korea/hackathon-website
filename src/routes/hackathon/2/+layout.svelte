<script>
    import { page } from '$app/stores';
    import { Button } from "flowbite-svelte";

    $: currentPath = $page.url.pathname;
    const base = '/hackathon/2';

    const tabs = [
        { label: 'Main', href: base },
        { label: 'Schedule', href: `${base}/schedule` },
        { label: 'Results', href: `${base}/results` },
    ];
</script>

<div
    class="bg-gray-900 text-white py-36"
    style="background: linear-gradient( rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6) ), no-repeat center / cover url('/cau.jpg');"
>
    <div class="container mx-auto text-center">
        <h1 class="text-3xl md:text-5xl font-bold mb-4">
            2nd Single Cell & Spatial Omics Hackathon
        </h1>
        <p class="md:text-2xl mb-8">
            Advancing Single-Cell and Spatial Omics Analysis
        </p>
        <Button
            href="https://zulip.scsok.io"
            target="_blank"
            size="xl"
            color="blue"><b>Join SCSOK Zulip</b></Button
        >
    </div>
</div>

<div class="bg-white border-b">
    <div class="container mx-auto">
        <nav class="flex space-x-1 px-8">
            {#each tabs as tab}
                <a
                    href={tab.href}
                    class="px-5 py-3 font-medium text-lg border-b-2 transition-colors
                        {currentPath === tab.href
                            ? 'border-blue-600 text-blue-600'
                            : 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-300'}"
                >
                    {tab.label}
                </a>
            {/each}
        </nav>
    </div>
</div>

<slot></slot>
