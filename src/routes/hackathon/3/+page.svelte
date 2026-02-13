<script>
    import { Button, Heading } from "flowbite-svelte";
    import { CalendarMonthSolid, MapPinAltSolid } from "flowbite-svelte-icons";
</script>

<div class="container mx-auto p-8 bg-white shadow-lg">
    <section id="about" class="mb-12">
        <Heading tag="h2" class="text-3xl font-bold mb-4">About the Hackathon</Heading>
        <p class="mb-4">
            The 3rd Single Cell & Spatial Omics Hackathon will be held at the
            Institute for Basic Science (IBS Science Culture Center) in Daejeon.
            Researchers, data scientists, and developers will collaborate in teams
            to analyze real single-cell and spatial omics datasets and develop
            prototype solutions.
        </p>
        <p class="mb-4">
            To ensure the hackathon addresses real scientific challenges, we are
            inviting submissions of any single-cell and spatial omics datasets.
            The goal is to bring together data that highlight important biological
            questions and analytical needs, providing participants with
            opportunities to test methods, create tools, and generate new insights.
        </p>
        <p>
            Submitted datasets should have a clear study design and include a short
            description of the biological context and research questions. The data
            must be shareable with all hackathon participants, although public release
            is not required. After review, five to ten datasets will be selected and
            used as the basis for team projects during the hackathon.
        </p>
        <div class="flex flex-col space-y-4 text-lg items-center mt-5">
            <div class="flex items-center">
                <CalendarMonthSolid class="w-6 h-6 mr-3 text-blue-600" />
                <span><strong>Date:</strong> February 9 - 13, 2026</span>
            </div>
            <div class="flex items-center">
                <MapPinAltSolid class="w-6 h-6 mr-3 text-red-600" />
                <span><strong>Location:</strong> IBS Science Culture Center, Daejeon</span>
            </div>
        </div>
        <div class="mt-5 text-lg text-center space-y-1">
            <p><strong>Host:</strong> Single Cell & Spatial Omics Korea (SCSOK)</p>
            <p><strong>Organizer:</strong> Institute for Basic Science (Center for Genome Engineering), Pusan National University (Interdisciplinary Major of Biodata Science Convergence), Soongsil University (G-LAMP AI-Bio Convergence Research Institute)</p>
        </div>
    </section>

    <section id="register" class="mb-12">
        <Heading tag="h2" class="text-3xl font-bold mb-4">Registration</Heading>
        <div class="space-y-4">
            <div class="bg-gray-50 p-6 rounded-lg shadow">
                <h3 class="text-xl font-semibold mb-2">For Bioinformaticians</h3>
                <p class="mb-3">
                    Register using the form below. The form collects your background,
                    experience, and research interests to match participants with
                    suitable teams and datasets.
                </p>
                <Button href="https://forms.gle/FurYADwzSaTZap1q9" target="_blank" size="sm" color="blue">Register as Bioinformatician</Button>
            </div>
            <div class="bg-gray-50 p-6 rounded-lg shadow">
                <h3 class="text-xl font-semibold mb-2">For Dataset Submission (PIs)</h3>
                <p class="mb-3">
                    Submit your dataset using the form below. The information gathered
                    will support project matching, reproducibility, and meaningful
                    exploration of analytical challenges.
                    The submission deadline is <strong>November 30, 2025</strong>.
                </p>
                <Button href="https://forms.gle/dj8eQ4xuDSrhSuCb6" target="_blank" size="sm" color="blue">Submit Dataset</Button>
            </div>
        </div>
    </section>

    <section id="event-website">
        <Heading tag="h2" class="text-3xl font-bold mb-4">Event Website</Heading>
        <p>
            For more details, visit the official event page:
            <Button href="https://events.kasra.kr/event/3" target="_blank" size="sm" color="blue">events.kasra.kr</Button>
        </p>
    </section>
</div>
