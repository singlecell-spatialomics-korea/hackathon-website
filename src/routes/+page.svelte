<script>
    import { Button, Heading } from "flowbite-svelte";
    import { CalendarMonthSolid, MapPinAltSolid } from "flowbite-svelte-icons";

    const hackathons = [
        {
            edition: "3rd",
            title: "3rd Single Cell & Spatial Omics Hackathon",
            subtitle: "Collaborate on Real Single-Cell and Spatial Omics Datasets",
            date: "February 9 - 13, 2026",
            location: "IBS Science Culture Center, Daejeon",
            href: "/hackathon/3",
        },
        {
            edition: "2nd",
            title: "2nd Single Cell & Spatial Omics Hackathon",
            subtitle: "Advancing Single-Cell and Spatial Omics Analysis",
            date: "February 17 - 21, 2025",
            location: "Chung-Ang University (DaVinci Campus), Anseong",
            href: "/hackathon/2",
        },
        {
            edition: "1st",
            title: "1st Single Cell & Spatial Omics Hackathon",
            subtitle: "Innovate in Single-Cell and Spatial Omics Data Analysis",
            date: "August 19 - 22, 2024",
            location: "Oceans and Fisheries HRD Institute, Gijang, Busan",
            href: "/hackathon/1",
        },
    ];
</script>

<div
    class="bg-gray-900 text-white py-36"
    style="background: linear-gradient( rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5) ), no-repeat center / cover url('/gijang.jpg');"
>
    <div class="container mx-auto text-center">
        <h1 class="text-3xl md:text-5xl font-bold mb-4">
            SCSOK Hackathon
        </h1>
        <p class="md:text-2xl mb-8">
            Single Cell & Spatial Omics Korea Hackathon Series
        </p>
        <Button
            href="https://zulip.scsok.io"
            target="_blank"
            size="xl"
            color="blue"><b>Join SCSOK Zulip</b></Button
        >
    </div>
</div>

<div class="container mx-auto p-8 bg-white shadow-lg">
    <section id="about" class="mb-12">
        <Heading tag="h2" class="text-3xl font-bold mb-4">About</Heading>
        <p class="mb-4">
            The SCSOK Hackathon series brings together experts, researchers, and
            data scientists in Korea in a collaborative setting to innovate in the
            fields of single-cell and spatial omics data analysis. Participants
            work with peers, engage with real-world datasets, and develop
            cutting-edge tools that provide deep insights into single-cell and
            spatially resolved biological data.
        </p>
    </section>

    <section id="hackathons" class="mb-12">
        <Heading tag="h2" class="text-3xl font-bold mb-6">Hackathons</Heading>
        <div class="grid gap-6">
            {#each hackathons as hackathon}
                <a href={hackathon.href} class="block group">
                    <div class="bg-gray-50 p-6 rounded-lg shadow hover:shadow-lg transition-shadow border-l-4 border-blue-600">
                        <h3 class="text-2xl font-semibold mb-2 group-hover:text-blue-600 transition-colors">
                            {hackathon.title}
                        </h3>
                        <p class="text-gray-600 mb-4">{hackathon.subtitle}</p>
                        <div class="flex flex-col sm:flex-row sm:space-x-8 space-y-2 sm:space-y-0 text-gray-700">
                            <div class="flex items-center">
                                <CalendarMonthSolid class="w-5 h-5 mr-2 text-blue-600" />
                                <span>{hackathon.date}</span>
                            </div>
                            <div class="flex items-center">
                                <MapPinAltSolid class="w-5 h-5 mr-2 text-red-600" />
                                <span>{hackathon.location}</span>
                            </div>
                        </div>
                    </div>
                </a>
            {/each}
        </div>
    </section>

    <section id="organizers" class="mb-12">
        <Heading tag="h2" class="text-3xl font-bold mb-4">Organizing Committee</Heading>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
            <div class="p-4 bg-gray-50 rounded-lg">
                <h3 class="text-xl font-semibold mb-2">Junil Kim</h3>
                <p>Soongsil University</p>
            </div>
            <div class="p-4 bg-gray-50 rounded-lg">
                <h3 class="text-xl font-semibold mb-2">Jeongbin Park</h3>
                <p>Pusan National University</p>
            </div>
            <div class="p-4 bg-gray-50 rounded-lg">
                <h3 class="text-xl font-semibold mb-2">Heetak Lee</h3>
                <p>Institute for Basic Science</p>
            </div>
        </div>
    </section>

    <section id="contact">
        <Heading tag="h2" class="text-3xl font-bold mb-4">Contact</Heading>
        <p class="mb-4">
            Interested in participating? This is an invitation-only event.
            Please reach out on the Zulip <code>hackathon</code> channel.
        </p>
    </section>
</div>
