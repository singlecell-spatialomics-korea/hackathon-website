<script>
    import { Heading } from 'flowbite-svelte';

    const teams = [
        { id: 'tenet', title: 'TENET+', track: 'singlecell' },
        { id: 'cnu', title: 'Human Heart Cell Analysis', track: 'spatial' },
        { id: 'colab', title: 'Best Practices for ST Data Analysis', track: 'spatial' },
        { id: 'kidney', title: 'Aging-Related Kidney Pathways', track: 'spatial' },
        { id: 'doublet', title: 'Doublet Classification via Topic Model', track: 'singlecell' },
        { id: 'brain', title: 'Spatial Cell-Cell Interaction in Mouse Brain', track: 'spatial' },
        { id: 'pseudobulk', title: 'Best Practices for Pseudobulk Analysis', track: 'singlecell' },
        { id: 'spatial-avengers', title: 'Spatial Domain Reconstruction', track: 'spatial' },
        { id: 'ssc', title: 'Spermatogonial Stem Cell Analysis', track: 'singlecell' },
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

                    <!-- Team 2: CNU Heart -->
                    <div id="cnu" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Human Heart Cell Analysis</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Systems Physiology Laboratory, College of Pharmacy, Chungnam National University
                            &middot; Topic: Spatial comparative analysis of cardiac tissue
                        </p>
                        <p class="text-gray-700 mb-4">
                            Performed spatial comparative analysis of human heart tissue using Visium data, focusing on three axes:
                            myocardium close to vs. far from endocardium, endocardium vs. myocardium, and right ventricle (RV) vs. left ventricle (LV).
                            Identified differentially expressed genes (DEGs) between cardiomyocytes and endothelial cells via volcano plot analysis.
                            Spatial mapping of cell-type-specific gene expression revealed that LV endocardium upregulates angiogenesis and vascular homeostasis genes,
                            while RV endocardium shows cardiac stress response genes. LV myocardium expressed genes related to muscle contraction (CSRP3, MYL2),
                            and RV myocardium showed structural stability genes. Concluded that LV and RV exhibit distinct gene expression patterns reflecting functional differences,
                            with potential utility for tracking heart disease progression.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/2nd/team2_slide5_img10.png" alt="Spatial cell type maps of heart tissue" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Spatial cell type mapping across cardiac regions</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/2nd/team2_slide10_img20.png" alt="Volcano plot: Cardiomyocyte vs Endothelial" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">DEGs between cardiomyocytes and endothelial cells</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 3: COLab (merged 3-1 + 3-2) -->
                    <div id="colab" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Best Practices for ST Data Analysis</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Abyot Melkamu Mekonnen, Hyeonmin Kim, Junseong Bae, Yuhui Jeong (COLab)
                            &middot; Topic: Visium HD &amp; Xenium analysis pipelines
                        </p>
                        <p class="text-gray-700 mb-4">
                            Developed comprehensive best-practice workflows for spatial transcriptomics data analysis across two goals:
                            (1) Visium HD analysis with SpatialData and napari, including data loading, cropping, multi-resolution plotting (2&micro;m and 16&micro;m bins),
                            and H&amp;E staining overlay with gene expression; and (2) Xenium analysis with Baysor cell segmentation integrated into Scanpy and SpatialData.
                            The Baysor pipeline converted 843K transcripts into 16,635 segmented cells. Additionally explored FICTURE for pixel-level spatial domain analysis
                            and Spapros for optimized probe set selection in targeted spatial transcriptomics experiments.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/2nd/team3_slide11_img25.png" alt="H&E staining with gene expression overlay" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Visium HD: H&amp;E + gene expression at 2&micro;m resolution</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/2nd/team3_slide27_img63.png" alt="FICTURE spatial domain analysis" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">FICTURE pixel-level spatial domain analysis on Visium HD CRC</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 4: Kidney Aging -->
                    <div id="kidney" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Triplet-Visium Reveals Aging-Related Kidney Pathways</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Geonhui Kang (KIOM), Yejin Gwak, Sohee Kim (Pusan National University)
                            &middot; Topic: Spatial analysis of kidney aging &amp; drug effects
                        </p>
                        <p class="text-gray-700 mb-4">
                            Analyzed triplet Visium spatial transcriptomics data from mouse kidney (Young, Old, Old+Drug) to identify aging-related pathways
                            and drug response effects. Applied batch correction with both Harmony and scVI, performed Leiden clustering, and selected regions of interest (ROIs)
                            using napari. Volcano plot analysis revealed DEGs between Young vs. Old and Old vs. Drug conditions.
                            GSEA identified key pathways including PPAR signaling and fatty acid degradation that were downregulated with aging
                            but partially rescued by drug treatment, suggesting potential therapeutic targets for age-related kidney dysfunction.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/2nd/team4_page14_img51.png" alt="Volcano plot: Young vs Old kidney" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Volcano plot of DEGs between Young and Old kidney</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/2nd/team4_page20_img69.jpeg" alt="PPAR signaling pathway" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">PPAR signaling pathway enriched in GSEA analysis</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 6: Mouse Brain -->
                    <div id="brain" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Spatial Cell-Cell Interaction in Mouse Brain</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Eunchae Kim, Hyeongseok Kim, Jebin Lee
                            &middot; Topic: Left-right brain asymmetry in cell-cell interaction
                        </p>
                        <p class="text-gray-700 mb-4">
                            Investigated spatial asymmetries and cell-cell interactions in mouse brain using Stereo-seq data.
                            Annotated cell types including astrocytes, cortical neurons, hippocampal neurons, dopaminergic neurons, oligodendrocytes,
                            and ventricular zone cells. CellChat analysis revealed strong cell-cell interactions in astrocytes with differential signaling
                            between left and right hemispheres. Glutamate and GABA were the most prevalent signals, with GABA displaying more prominent
                            outgoing signaling in the right hemisphere astrocytes. APP signaling was significantly decreased in the right hemisphere,
                            suggesting functional variations in brain organization despite similar cell-type composition.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/2nd/team6_slide8_img11.png" alt="Annotated cell types on mouse brain" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Annotated cell types on mouse brain coronal section</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/2nd/team6_slide10_img15.png" alt="Left-right signaling heatmap" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Incoming signaling patterns: left vs. right hemisphere</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 8: Spatial Avengers -->
                    <div id="spatial-avengers" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Spatial Domain Reconstruction</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Jahanzeb Saqib (Prof. Junil Kim)
                            &middot; Topic: Predicting neighboring spatial spots using foundation models
                        </p>
                        <p class="text-gray-700 mb-4">
                            Developed a transformer-based foundation model approach for predicting neighboring spatial spots from single-spot gene expression.
                            Used Xenium brain and ovary datasets (21,651 spots, 979 genes, 7 cell types) with neighborhood calculation based on 20&micro;m distance.
                            Implemented two prediction methods: existence prediction (whether a neighbor exists) and exact neighbor prediction.
                            The model achieved over 85% test accuracy across diverse cell types, demonstrating the feasibility of
                            spatial domain reconstruction from gene expression data using large language model architectures.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/2nd/team8_slide8_img36.png" alt="Spatial domain slide plot" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Spatial slide plot with predicted cell type domains</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/2nd/team8_slide9_img39.png" alt="Test accuracy per cell type" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Test accuracy for each cell type (>85% across types)</figcaption>
                            </figure>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Single-cell Transcriptomics Track -->
            <section>
                <h3 class="text-2xl font-bold mb-6 pb-2 border-b-2 border-blue-600">Single-cell Transcriptomics</h3>
                <div class="space-y-10">

                    <!-- Team 1: TENET+ -->
                    <div id="tenet" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">TENET+</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Topic: Gene regulatory network inference from multiome data
                        </p>
                        <p class="text-gray-700 mb-4">
                            Applied TENET+, a gene regulatory network (GRN) inference tool, to PBMC multiome (scRNA-seq + scATAC-seq) data.
                            Constructed GRN triplets linking transcription factors (TFs), target genes (TGs), and TF-associated regulatory elements (TARs)
                            using transfer entropy-based scoring. TripletTrimming refined the network by incorporating chromatin accessibility and genomic distance.
                            Degree analysis of the trimmed B-cell GRN identified JUNB (657 targets), IKZF3 (654), and POU2F2 (597) as top hub TFs.
                            Pseudo-heatmap and network visualizations confirmed biologically relevant TF&ndash;target relationships.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/2nd/team1_img5.png" alt="Top TF outdegree in B-cell GRN" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Top TF outdegree after TripletTrimming</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/2nd/team1_img9.png" alt="GRN network visualization" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">GRN network: TFs, target genes, and regulatory elements</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 5: Doublet -->
                    <div id="doublet" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Doublet Classification using Topic Model</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Kanghee Cho, Seulgi Lee, Chanho Park, Junyoung Kim (Laboratory for Single Cell Systems, Soongsil University)
                            &middot; Topic: Novel doublet detection approach
                        </p>
                        <p class="text-gray-700 mb-4">
                            Proposed a topic-model-based approach for doublet detection in scRNA-seq data. The hypothesis is that cells exhibiting
                            unexpected co-expression of markers from multiple cell types are likely doublets. Applied topic modeling to assign each cell
                            a topic distribution, where each topic corresponds to a cell type (validated via EnrichR).
                            Compared topic assignments with Leiden clustering and identified cases where topic 9 cells (Red Blood Cell markers: HBB)
                            were spatially dispersed in UMAP space. Demonstrated detection of doublets (e.g., RBC+B cell, RBC+Monocyte marker co-expression)
                            that were missed by existing tools like Scrublet and DoubletDetection.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/2nd/team5_slide8_img17.png" alt="Topic modeling concept for doublet detection" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Topic modeling concept for doublet detection</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/2nd/team5_slide10_img29.png" alt="Leiden clustering UMAP comparison" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Leiden clustering comparison with topic model results</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 7: Pseudobulk -->
                    <div id="pseudobulk" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Best Practices for Pseudobulk Analysis</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Youngchul Oh, Yeongjun Kim
                            &middot; Topic: Optimizing pseudobulk DEG detection in scRNA-seq
                        </p>
                        <p class="text-gray-700 mb-4">
                            Systematically evaluated how pseudobulk sample size and count parameters affect differential expression gene (DEG) detection quality
                            in scRNA-seq data. Compared pseudobulk DEGs against gold-standard bulk RNA-seq results across 16 comparisons from multiple datasets
                            (Angelidis2019, CanoGamez2020, Hagai2018). Demonstrated that larger pseudobulk sample sizes consistently improve DEG detection F1-scores.
                            The approach recovers dropout events to some extent and outperforms single-cell-level DEG analysis. Also tested on Tabula Muris mouse cell atlas,
                            confirming that pseudobulk correctly identifies marker genes (e.g., alveolar macrophage markers Cd68, Marco, Pparg)
                            and improves with increasing sample size.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/2nd/team7_slide7_img14.png" alt="F1-score by pseudobulk sample size" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">F1-score increases with larger pseudobulk sample size</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/2nd/team7_slide8_img16.png" alt="F1-score across datasets" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">F1-score comparison across multiple datasets</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 9: SSC -->
                    <div id="ssc" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Spermatogonial Stem Cell Analysis</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Lab of Animal Biotechnology, Department of Animal Science &amp; Technology, Chung-Ang University
                            &middot; Topic: scRNA-seq analysis of spermatogonial stem cells
                        </p>
                        <p class="text-gray-700 mb-4">
                            Analyzed scRNA-seq data to characterize spermatogonial stem cells (SSCs), which constitute only 0.03% of mouse testis cells.
                            Performed quality control, Leiden clustering, and UMAP visualization to identify cell populations. Validated SSC markers
                            including Id4 and Lhx1. Pseudotime analysis revealed pathway activation in energy metabolism (glycolysis, oxidative phosphorylation),
                            cell signaling (oxidative stress response), and spermatogenesis-specific genes (Stk31). Cell cycle gene regression and RNA velocity
                            analysis were applied to distinguish true SSCs (1&ndash;2% of the SSC population) from other spermatogonial cells,
                            aiming to discover new SSC-specific markers for efficient purification.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/2nd/team9_slide9_img23.png" alt="Leiden clustering UMAP" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Leiden clustering of spermatogonial cells</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/2nd/team9_slide9_img24.png" alt="SSC score on UMAP" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">SSC score projection on UMAP</figcaption>
                            </figure>
                        </div>
                    </div>

                </div>
            </section>
        </div>
    </div>
</div>
