<script>
    import { Button, Heading } from "flowbite-svelte";
    import { CalendarMonthSolid, MapPinAltSolid } from "flowbite-svelte-icons";

    const organizers = [
        { name: "Junil Kim", affiliation: "Soongsil University" },
        { name: "Jeongbin Park", affiliation: "Pusan National University" },
        { name: "Heetak Lee", affiliation: "Institute for Basic Science" },
    ];
</script>

<div
    class="bg-gray-900 text-white py-36"
    style="background: linear-gradient( rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5) ), no-repeat center / cover url('/gijang.jpg');"
>
    <div class="container mx-auto text-center">
        <h1 class="text-3xl md:text-5xl font-bold mb-4">
            1st Single Cell & Spatial Omics Hackathon
        </h1>
        <p class="md:text-2xl mb-8">
            Innovate in Single-Cell and Spatial Omics Data Analysis
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
        <Heading tag="h2" class="text-3xl font-bold mb-4"
            >About the Hackathon</Heading
        >
        <p class="mb-4">
            Welcome to the 1st Single Cell & Spatial Omics Hackathon, to be held
            at the Oceans and Fisheries HRD Institute in Gijang, Busan. This
            exciting event will bring together experts, researchers, and data
            scientists in Korea in a collaborative setting to innovate in the
            fields of single-cell and spatial omics data analysis.
        </p>
        <p>
            By joining this hackathon, you'll have the chance to work with
            peers, engage with real-world datasets, and develop cutting-edge
            tools that provide deep insights into single-cell and spatially
            resolved biological data.
        </p>
        <div class="flex flex-col space-y-4 text-lg items-center mt-5">
            <div class="flex items-center">
                <CalendarMonthSolid class="w-6 h-6 mr-3 text-blue-600" />
                <span
                    ><strong>Date:</strong> August 19, 2024 - August 22, 2024</span
                >
            </div>
            <div class="flex items-center">
                <MapPinAltSolid class="w-6 h-6 mr-3 text-red-600" />
                <span
                    ><strong>Location:</strong> Oceans and Fisheries HRD Institute,
                    Gijang, Busan</span
                >
            </div>
        </div>
    </section>

    <section id="agenda" class="mb-12">
        <Heading tag="h2" class="text-3xl font-bold mb-6">Agenda</Heading>
        <div class="grid md:grid-cols-2 gap-6">
            <div class="bg-gray-50 p-6 rounded-lg shadow">
                <h3 class="text-2xl font-semibold mb-4">
                    Spatial Transcriptomics
                </h3>
                <ul class="space-y-2">
                    <li class="flex items-start">
                        <svg
                            class="w-6 h-6 mr-2 flex-shrink-0"
                            fill="none"
                            stroke="currentColor"
                            viewBox="0 0 24 24"
                            xmlns="http://www.w3.org/2000/svg"
                            ><path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 5l7 7-7 7"
                            ></path></svg
                        >
                        <span
                            >Cell segmentation of high resolution ST data (e.g.,
                            Visium HD)</span
                        >
                    </li>
                    <li class="flex items-start">
                        <svg
                            class="w-6 h-6 mr-2 flex-shrink-0"
                            fill="none"
                            stroke="currentColor"
                            viewBox="0 0 24 24"
                            xmlns="http://www.w3.org/2000/svg"
                            ><path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 5l7 7-7 7"
                            ></path></svg
                        >
                        <span
                            >Neighbor-specific alteration of gene expression</span
                        >
                    </li>
                    <li class="flex items-start">
                        <svg
                            class="w-6 h-6 mr-2 flex-shrink-0"
                            fill="none"
                            stroke="currentColor"
                            viewBox="0 0 24 24"
                            xmlns="http://www.w3.org/2000/svg"
                            ><path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 5l7 7-7 7"
                            ></path></svg
                        >
                        <span>Tissue territory/domain analysis</span>
                    </li>
                    <li class="flex items-start">
                        <svg
                            class="w-6 h-6 mr-2 flex-shrink-0"
                            fill="none"
                            stroke="currentColor"
                            viewBox="0 0 24 24"
                            xmlns="http://www.w3.org/2000/svg"
                            ><path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 5l7 7-7 7"
                            ></path></svg
                        >
                        <span>Integration</span>
                    </li>
                </ul>
            </div>
            <div class="bg-gray-50 p-6 rounded-lg shadow">
                <h3 class="text-2xl font-semibold mb-4">
                    Single-cell Transcriptomics
                </h3>
                <ul class="space-y-2">
                    <li class="flex items-start">
                        <svg
                            class="w-6 h-6 mr-2 flex-shrink-0"
                            fill="none"
                            stroke="currentColor"
                            viewBox="0 0 24 24"
                            xmlns="http://www.w3.org/2000/svg"
                            ><path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 5l7 7-7 7"
                            ></path></svg
                        >
                        <span>Application of AI, e.g., GPTs</span>
                    </li>
                    <li class="flex items-start">
                        <svg
                            class="w-6 h-6 mr-2 flex-shrink-0"
                            fill="none"
                            stroke="currentColor"
                            viewBox="0 0 24 24"
                            xmlns="http://www.w3.org/2000/svg"
                            ><path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 5l7 7-7 7"
                            ></path></svg
                        >
                        <span>Lineage tracing</span>
                    </li>
                    <li class="flex items-start">
                        <svg
                            class="w-6 h-6 mr-2 flex-shrink-0"
                            fill="none"
                            stroke="currentColor"
                            viewBox="0 0 24 24"
                            xmlns="http://www.w3.org/2000/svg"
                            ><path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 5l7 7-7 7"
                            ></path></svg
                        >
                        <span>Sane method for HVG selection</span>
                    </li>
                    <li class="flex items-start">
                        <svg
                            class="w-6 h-6 mr-2 flex-shrink-0"
                            fill="none"
                            stroke="currentColor"
                            viewBox="0 0 24 24"
                            xmlns="http://www.w3.org/2000/svg"
                            ><path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 5l7 7-7 7"
                            ></path></svg
                        >
                        <span>Genotype to phenotype inference</span>
                    </li>
                </ul>
            </div>
        </div>
    </section>

    <section id="organizers" class="mb-12">
        <Heading tag="h2" class="text-3xl font-bold mb-4"
            >Organizing Committee</Heading
        >
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
            {#each organizers as organizer}
                <div class="p-4 bg-gray-50 rounded-lg">
                    <h3 class="text-xl font-semibold mb-2">
                        {organizer.name}
                    </h3>
                    <p>{organizer.affiliation}</p>
                </div>
            {/each}
        </div>
    </section>

    <section id="register">
        <Heading tag="h2" class="text-3xl font-bold mb-4">Registration</Heading>
        <p class="mb-4">
            Please note that this is an invitation-only event. If you are
            interested, please reach out on the Zulip `hackathon` channel.
        </p>
    </section>
</div>
