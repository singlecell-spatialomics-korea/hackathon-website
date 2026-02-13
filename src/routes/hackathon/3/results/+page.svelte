<script>
    import { Heading } from 'flowbite-svelte';

    const teams = [
        { id: 'tf-isoform', title: 'Spatial TF–Isoform Regulatory Programs', track: 'spatial' },
        { id: 'spatial-domain', title: 'Spatial Domain Reconstruction', track: 'spatial' },
        { id: 'visium-stomics', title: 'Visium Platform & Stereo-seq Analysis', track: 'spatial' },
        { id: 'st-benchmark', title: 'ST Foundation Model Benchmarking', track: 'spatial' },
        { id: 'longread-st', title: 'Long-Read Spatial Transcriptomics', track: 'spatial' },
        { id: 'cluster-merging', title: 'DEG-Based Iterative Cluster Merging', track: 'singlecell' },
        { id: 'virtual-cell', title: 'Virtual Cell: Tahoe-100M & scGPT', track: 'singlecell' },
        { id: 'openclaw', title: 'OpenClaw AI Data Scientist', track: 'singlecell' },
        { id: 'fm-subtype', title: 'Foundation Model Subtype Benchmarking', track: 'singlecell' },
    ];

    $: spatialTeams = teams.filter(t => t.track === 'spatial');
    $: scTeams = teams.filter(t => t.track === 'singlecell');
</script>

<div class="container mx-auto bg-white shadow-lg">
    <div class="flex flex-col md:flex-row">
        <!-- Sidebar -->
        <nav class="md:w-64 flex-shrink-0 p-6 md:border-r border-gray-200">
            <div class="sticky top-4 space-y-4">
                <div>
                    <h4 class="text-sm font-bold text-gray-400 uppercase tracking-wider mb-2">Spatial Transcriptomics</h4>
                    <ul class="space-y-1">
                        {#each spatialTeams as team}
                            <li>
                                <a href="#{team.id}" class="block px-3 py-1.5 text-sm rounded hover:bg-blue-50 hover:text-blue-600 text-gray-700 transition-colors">
                                    {team.title}
                                </a>
                            </li>
                        {/each}
                    </ul>
                </div>
                <div>
                    <h4 class="text-sm font-bold text-gray-400 uppercase tracking-wider mb-2">Single-cell Transcriptomics</h4>
                    <ul class="space-y-1">
                        {#each scTeams as team}
                            <li>
                                <a href="#{team.id}" class="block px-3 py-1.5 text-sm rounded hover:bg-blue-50 hover:text-blue-600 text-gray-700 transition-colors">
                                    {team.title}
                                </a>
                            </li>
                        {/each}
                    </ul>
                </div>
            </div>
        </nav>

        <!-- Main Content -->
        <div class="flex-1 min-w-0 p-8 space-y-12">
            <Heading tag="h2" class="text-3xl font-bold mb-8">Results</Heading>

            <!-- Spatial Transcriptomics Track -->
            <section>
                <h3 class="text-2xl font-bold mb-6 pb-2 border-b-2 border-blue-600">Spatial Transcriptomics</h3>
                <div class="space-y-10">

                    <!-- Team 1: Korea University -->
                    <div id="tf-isoform" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Spatially Structured TF&ndash;Isoform Regulatory Programs in Mouse Cortex</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Inkyung Ko, Gaeun Byun, Dabin Lee, Seoyeon Lee, Haeun Jung, Youngseok Choi, Heesun Choi (Korea University)
                            &middot; Topic: TF&ndash;isoform spatial regulation in cortex
                        </p>
                        <p class="text-gray-700 mb-4">
                            Developed a comprehensive pipeline for analyzing spatially structured TF&ndash;isoform regulatory programs
                            in mouse cortex using 10x Visium HD data. Quantified isoforms at the spot-level (16&micro;m bins) and inferred
                            TF regulon activity via pySCENIC, identifying 95 significant regulons. Introduced the TIE (TF-Isoform Effect)
                            score integrating PSI, gene expression, and TF activity, and applied Moran's I spatial autocorrelation analysis
                            to identify 63,804 spatially variable TF&ndash;isoform pairs. Layer-specific analysis revealed distinct isoform
                            switching patterns, such as Calm1 isoforms regulated by Tef across cortical layers. Also developed ASAP,
                            a RAG-based agentic AI platform for end-to-end spatial transcriptomics analysis.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/3rd/team1_slide11_img12.png" alt="Top 15 TF regulons with layer breakdown" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Top 15 TF regulons by isoform-TF pair count across cortical layers</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/3rd/team1_slide13_img14.png" alt="Calm1 isoform-specific TIE scores across layers" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Calm1&ndash;Tef isoform-specific TIE scores showing layer-dependent switching</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 3: Spatial Domain Reconstruction -->
                    <div id="spatial-domain" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Spatial Domain Reconstruction &amp; Niche Gene Analysis</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Jahanzeb Saqib (Laboratory for Single Cell Systems, Prof. Junil Kim, Soongsil University)
                            &middot; Topic: Predicting spatial neighbors using transformer architecture
                        </p>
                        <p class="text-gray-700 mb-4">
                            Built a cancer-biology-specialized transformer model for spatial neighborhood prediction and niche gene analysis
                            using Xenium data from 4 cancer types (breast, lung, ovarian, pancreatic) across 7 slides (~1M spots, ~5K genes).
                            The model encodes gene expression, metadata, and neighbor cell type information into a unified sentence representation,
                            inspired by NicheFormer and scGPT architectures. Achieved ~77% accuracy in spatial data predictions for cell type
                            label transfer and neighborhood composition. Demonstrated effectiveness in identifying niche genes
                            influencing spatial interactions in the tumor microenvironment, with potential for perturbation prediction.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/3rd/team3_slide19_img32.png" alt="Model architecture overview" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Graphical abstract: spatial neighbor prediction pipeline</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/3rd/team3_slide29_img75.png" alt="Evaluation of prediction accuracy" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Evaluation: accuracy and MSE for binary and counting predictions</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 5: IBS BIS Lab -->
                    <div id="visium-stomics" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Visium Platform Comparison &amp; Stereo-seq Analysis</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Yeongjun Kim, Ohbin Kwon, Onyu Shin (BIS Lab, Center for Genome Engineering, IBS)
                            &middot; Topic: Comparing Visium capture methods &amp; Stereo-seq disease analysis
                        </p>
                        <p class="text-gray-700 mb-4">
                            Conducted a systematic comparison of Visium platform configurations: OCT Manual (Poly-A capture),
                            OCT CytAssist, FFPE Manual, and FFPE CytAssist (all Probe-based) on mouse spleen tissue.
                            Demonstrated that probe-based methods yield significantly higher UMI counts and mapping confidence (85&ndash;98%)
                            compared to Poly-A (66&ndash;79%), while Poly-A uniquely detects non-probe genes (e.g., Hba-a1, a red pulp marker).
                            Additionally performed hands-on Stereo-seq analysis of brain tissue at sub-cellular resolution,
                            showing that white matter sublayer size decreases with disease progression across control, moderate, and severe conditions.
                        </p>
                        <div class="grid grid-cols-1 gap-4">
                            <figure>
                                <img src="/results/3rd/team5_slide16_img100.png" alt="Spatial Leiden clustering across mouse spleen samples" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Spatial Leiden clustering across Visium spleen samples (4 capture configurations)</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 7: ST Foundation Model Benchmarking -->
                    <div id="st-benchmark" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Spatial Transcriptomics Foundation Model Benchmarking</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Gahyun Kim, Hyun Seo Lee, Cherin Lee (Laboratory for Single Cell Systems, Prof. Junil Kim, Soongsil University)
                            &middot; Topic: Benchmarking deconvolution &amp; super-resolution methods
                        </p>
                        <p class="text-gray-700 mb-4">
                            Systematically benchmarked spatial transcriptomics foundation models for deconvolution and super-resolution
                            using Xenium-derived pseudovisium data from human CRC as ground truth. Evaluated TransformerST (super-resolution),
                            Loki OmiCLIP (multimodal deconvolution), scGPT-Spatial (embedding-based deconvolution), and cell2location.
                            TransformerST failed to recover sparsity patterns during super-resolution. Loki's pretrained text embeddings
                            could not distinguish cell types (cosine similarity ~1 across types). scGPT-Spatial achieved the best performance
                            with PCC &gt; 0.8 for major cell types (Epithelial, Tumor_CMS, Stromal_Mesenchymal), while cell2location
                            showed more robust performance for rare cell types.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/3rd/team7_page7_img15.jpeg" alt="CRC spatial cell type prediction map" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">CRC spatial cell type prediction (large type) on pseudovisium</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/3rd/team7_page19_img49.jpeg" alt="Cell type composition per spot" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">scGPT-Spatial: cell type composition per spot</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 8: PNU COLab Long-Read -->
                    <div id="longread-st" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Long-Read Spatial Transcriptomics: Structural Variants &amp; Isoform Analysis</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Hyeon-Min Kim, Junseong Bae, Sohui Kim, Yuhui Jeong (PNU COLab)
                            &middot; Topic: Long-read Visium HD analysis pipeline
                        </p>
                        <p class="text-gray-700 mb-4">
                            Developed an analysis pipeline for long-read Visium HD spatial transcriptomics data, covering three domains:
                            (1) Basic analysis with Tangram-based cell typing using annotated single-cell reference data;
                            (2) Spatial distribution of structural variants (SVs) detected via Sniffles2 (931 SVs) and cuteSV (9,058 SVs),
                            plus gene fusion detection via JAFFAL (270 fusions), all spatially mapped to tissue coordinates;
                            (3) Isoform-level spatial analysis using stLENS, revealing isoform-specific spatial patterns
                            (e.g., Myl6 isoforms differentially expressed between ventricle and hippocampal neurons).
                            Also applied SUPPA2 and SpliZ for splicing event analysis, proposing a workflow for spatial long-read
                            splicing analysis.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/3rd/team8_page7_img2.jpg" alt="Spatial distribution of top structural variants" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Top 20 SVs by support mapped to tissue (INS, DUP, DEL, INV)</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/3rd/team8_page11_img3.jpg" alt="Myl6 isoform spatial expression" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Myl6 isoform-specific spatial expression pattern</figcaption>
                            </figure>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Single-cell Transcriptomics Track -->
            <section>
                <h3 class="text-2xl font-bold mb-6 pb-2 border-b-2 border-blue-600">Single-cell Transcriptomics</h3>
                <div class="space-y-10">

                    <!-- Team 2: DEG-Based Cluster Merging -->
                    <div id="cluster-merging" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">DEG-Based Iterative Cluster Merging for Sub-Cell Type Annotation</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Chaewon Kim, Seungyoon Song (Laboratory for Single Cell Systems, Prof. Junil Kim, Soongsil University)
                            &middot; Topic: Automated sub-cell type cluster optimization
                        </p>
                        <p class="text-gray-700 mb-4">
                            Developed an iterative cluster merging algorithm to achieve optimal sub-cell type annotation with minimal manual effort.
                            Starting from high-resolution Leiden clustering (resolution=3), the method computes pairwise DEGs between all clusters
                            (FDR &lt; 0.05, logFC &gt; 3), ranks pairs by ascending DEG count, and iteratively merges the top 5% most similar pairs.
                            Tie-breaking uses centroid distance in embedding space. Applied to pan-cancer T-cell data, the algorithm
                            reduced 42 initial clusters to biologically meaningful sub-cell types over 3 iterations, recovering known populations
                            including NK/NKT, MAIT, Treg, Th17, Tfh, and exhausted CD4/CD8 subtypes.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/3rd/team2_slide11_img34.png" alt="UMAP after iteration 3 cluster merging" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">UMAP after iteration 3 of cluster merging</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/3rd/team2_slide11_img35.png" alt="Final cell type annotation UMAP" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Final sub-cell type annotation (T-cell subtypes)</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 4: Virtual Cell / scGPT -->
                    <div id="virtual-cell" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Virtual Cell: Tahoe-100M Data Analysis &amp; scGPT Fine-Tuning</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Hyeonkyu Kim, Kanghee Cho, Seongmi Woo, Dohyun Lee, Seokwon Kim, Junil Kim, Daewon Lee, Sangmin Park
                            (Soongsil University, Chung-Ang University, Chungnam National University)
                            &middot; Topic: Drug perturbation prediction with scGPT
                        </p>
                        <p class="text-gray-700 mb-4">
                            Explored virtual cell modeling by analyzing the Tahoe-100M large-scale drug perturbation dataset (429GB)
                            and training scGPT for drug response prediction. Preprocessed the data by converting drug targets to CRISPR-style
                            conditions for scGPT compatibility, using a single cell line (CVCL_0546) with 379 drugs.
                            Compared fine-tuning a pretrained scGPT model versus training from scratch. Fine-tuned models showed
                            improved UMAP overlap between predicted and ground truth gene expression distributions,
                            though limitations remain in data representativeness and biological validation of predictions.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/3rd/team4_slide12_img21.png" alt="UMAP: scratch model prediction vs truth" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">From-scratch model: predicted vs ground truth UMAP</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/3rd/team4_slide12_img22.png" alt="UMAP: fine-tuned model prediction vs truth" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Fine-tuned model: improved overlap with ground truth</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 6: OpenClaw AI Agent -->
                    <div id="openclaw" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">OpenClaw-Based AI Data Scientist</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Minseong Woo (PNU COLab)
                            &middot; Topic: AI agent for automated single-cell &amp; spatial analysis
                        </p>
                        <p class="text-gray-700 mb-4">
                            Developed an AI-powered data scientist agent based on OpenClaw, a technology that enables AI to directly control
                            computer interfaces (mouse, keyboard, screen). The system accepts analysis requests via Discord messages and
                            autonomously executes reproducible analysis pipelines. It comprises specialized sub-agents (sc-agent, spatial-agent,
                            web-browsing-agent, coding-agent) powered by local LLMs (gpt-oss-120B, gemma3-27B) and Claude API,
                            connected via MCP servers. The workflow routes data to appropriate agents, executes analysis skills,
                            and reports progress every 5 minutes. Demonstrated live on mouse brain fixed single-cell data,
                            performing clustering (29 clusters), CellTypist annotation, and DEG analysis automatically.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/3rd/team6_slide6_img15.jpg" alt="Discord interaction with OpenClaw agent" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Discord-based interaction: data listing via OpenClaw</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/3rd/team6_slide7_img18.jpg" alt="Automated analysis results from AI agent" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Automated clustering &amp; CellTypist annotation output</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 9: Foundation Model Subtype Benchmarking -->
                    <div id="fm-subtype" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Foundation Model Benchmarking for Cell Subtype Annotation</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Jaewoo Mo, Jiyeon Park (Laboratory for Single Cell Systems, Prof. Junil Kim, Soongsil University)
                            &middot; Topic: Evaluating scGPT &amp; scFoundation for high-resolution subtype recovery
                        </p>
                        <p class="text-gray-700 mb-4">
                            Systematically benchmarked pretrained foundation models (scGPT and scFoundation) for their ability to recover
                            high-resolution cell subtypes without fine-tuning. Used large-scale pan-cancer (2.3M cells, 91 subtypes)
                            and cardiac (2.4M cells, 39 subtypes) single-cell atlases as references, splitting 70/30 for reference/query
                            with label masking. Generated embeddings via scGPT and scFoundation, performed label transfer via BBKNN and scVI,
                            and compared predictions against manual annotations. Found that pretrained models perform well on marker-defined
                            discrete subtypes but struggle with continuum/process-driven functional subtypes,
                            highlighting the limits of foundation model generalization for fine-grained cell annotation.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/3rd/team9_slide6_img13.png" alt="Endothelial cell subtype UMAP" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Heart endothelial cell subtypes (reference annotation)</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/3rd/team9_slide11_img22.png" alt="Foundation model subtype prediction limitations" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Pretrained models: accurate on discrete subtypes, poor on continuum-driven ones</figcaption>
                            </figure>
                        </div>
                    </div>

                </div>
            </section>
        </div>
    </div>
</div>
