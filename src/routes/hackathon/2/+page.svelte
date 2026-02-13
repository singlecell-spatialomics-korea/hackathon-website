<script>
    import { Button, Heading } from "flowbite-svelte";
    import { CalendarMonthSolid, MapPinAltSolid } from "flowbite-svelte-icons";

    const organizers = [
        { name: "Junil Kim", affiliation: "Soongsil University" },
        { name: "Daewon Lee", affiliation: "Chung-Ang University" },
        { name: "Jieun Jeong", affiliation: "Soongsil University" },
    ];
</script>

<div class="container mx-auto p-8 bg-white shadow-lg">
    <section id="about" class="mb-12">
        <Heading tag="h2" class="text-3xl font-bold mb-4">About the Hackathon</Heading>
        <p class="mb-4">
            Welcome to the 2nd Single Cell & Spatial Omics Hackathon, taking place
            from February 17-21, 2025, at Chung-Ang University's DaVinci Campus in
            Anseong, Gyeonggi-do. This event is jointly hosted by Soongsil University,
            Single Cell & Spatial Omics Korea (SCSOK), and Korea Bio Research
            Association (KOBRA).
        </p>
        <p class="mb-4">
            The hackathon convened experts, researchers, and data scientists from
            across Korea in a dynamic collaborative environment to advance innovation
            in single-cell and spatial omics data analysis. Participants had the
            opportunity to work alongside peers on real-world datasets, developing
            cutting-edge analytical tools that provide profound insights into
            single-cell and spatially resolved biological data.
        </p>
        <p>
            As rapidly evolving fields driven by technological advancement and the
            growing demand for sophisticated analysis methods, single-cell and spatial
            omics represent crucial areas for scientific progress. This hackathon served
            as an essential platform for interdisciplinary collaboration, bringing
            together professionals from bioinformatics, software development, and
            spatial biology in Korea.
        </p>
        <div class="flex flex-col space-y-4 text-lg items-center mt-5">
            <div class="flex items-center">
                <CalendarMonthSolid class="w-6 h-6 mr-3 text-blue-600" />
                <span><strong>Date:</strong> February 17 - 21, 2025</span>
            </div>
            <div class="flex items-center">
                <MapPinAltSolid class="w-6 h-6 mr-3 text-red-600" />
                <span><strong>Location:</strong> Chung-Ang University (DaVinci Campus), Anseong, Gyeonggi-do</span>
            </div>
        </div>
        <div class="mt-5 text-lg text-center">
            <p><strong>Host:</strong> Soongsil University, Single Cell & Spatial Omics Korea (SCSOK), Korea Bio Research Association (KOBRA)</p>
        </div>
    </section>

    <section id="organizers" class="mb-12">
        <Heading tag="h2" class="text-3xl font-bold mb-4">Organizing Committee</Heading>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
            {#each organizers as organizer}
                <div class="p-4 bg-gray-50 rounded-lg">
                    <h3 class="text-xl font-semibold mb-2">{organizer.name}</h3>
                    <p>{organizer.affiliation}</p>
                </div>
            {/each}
        </div>
    </section>

    <section id="register">
        <Heading tag="h2" class="text-3xl font-bold mb-4">Registration</Heading>
        <p class="mb-4">
            Registration for this event was available at
            <Button href="https://kobra.kr/REGISTRATION" target="_blank" size="sm" color="blue">KOBRA Registration</Button>
        </p>
    </section>
</div>
