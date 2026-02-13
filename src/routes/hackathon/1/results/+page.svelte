<script>
    import { Heading } from 'flowbite-svelte';

    const teams = [
        { id: 'spatial-causality', title: 'Spatial Causality', track: 'spatial' },
        { id: 'superpixels', title: 'Superpixels on Vesalius', track: 'spatial' },
        { id: 'gist', title: 'Tumor Subpopulation Spatial Analysis', track: 'spatial' },
        { id: 'geninus-skku', title: 'Visium HD & Xenium Integration', track: 'spatial' },
        { id: 'pnu', title: 'Fast and Scalable SSAM', track: 'spatial' },
        { id: 'kribb', title: 'Spatial Embedding of scRNA-seq', track: 'spatial' },
        { id: 'ibs', title: 'BarGS', track: 'singlecell' },
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

                    <!-- Team 1: Spatial Causality -->
                    <div id="spatial-causality" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Spatial Causality</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Jeonghwan Kim, Hyun Seo Lee, Seulki Lee, Hoebin Chung
                            &middot; Topic: Neighbor-specific alteration of gene expression
                        </p>
                        <p class="text-gray-700 mb-4">
                            Explored spatial causality in spatial transcriptomics by adapting econometric causality frameworks to Visium HD data (P5 CRC dataset).
                            To handle the computational cost of high-resolution VisiumHD, the team developed three strategies: grid selection (cropping informative
                            regions with diverse cell type compositions via deconvolution), gene selection (focusing on ligand-receptor pairs and GO molecular
                            function terms), and GPU acceleration using CUDA on an RTX A5000. These optimizations reduced execution time from 1 hour (single-core)
                            to 5 minutes (multi-core) to 1 second (GPU), enabling scalable spatial causality analysis to identify neighbor-specific
                            alterations of gene expression across cell types.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/1st/team1_slide8_img1.png" alt="Grid selection on VisiumHD CRC dataset" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Grid selection: 4 crop regions with deconvolution labels</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/1st/team1_slide11_img1.png" alt="Ligand-receptor spatial expression analysis" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Ligand-receptor spatial expression (APP, CD74)</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 3: Superpixels on Vesalius -->
                    <div id="superpixels" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Superpixels on Vesalius</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Patrick C. N. Martin (Cedars-Sinai Medical Center), Hwisoo Choi, Hyeonkyu Kim, Jaeowoo Mo, Taehong Min, Jiyeon Park (Soongsil University)
                            &middot; Topic: Tissue territory/domain analysis
                        </p>
                        <p class="text-gray-700 mb-4">
                            Developed a superpixel-based approach on top of the Vesalius framework to create expression-aware spatial bulks from Visium HD data.
                            The team converted spatial transcriptome data into an RGB color-embedded image space, then applied SLIC-based superpixel clustering
                            (K-means, Louvain, and Leiden variants) to generate pseudo-bulk expression profiles at varying resolutions.
                            Compared clustering results between Visium HD single-cell spots (~129k), superpixel bulks (~12k and ~200), and showed
                            superpixels recover tissue domain structure while enabling faster downstream analysis. Ontology enrichment (DisGeNET) validated
                            that superpixel bulks capture disease-relevant signals comparable to full-resolution data.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/1st/team3_img51.jpeg" alt="RGB space with superpixels on tissue" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Superpixel clustering in RGB-embedded space</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/1st/team3_img67.png" alt="Ontology heatmap comparing Visium, Visium HD, and superpixels" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">DisGeNET ontology heatmap across resolutions</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 5: GIST -->
                    <div id="gist" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Tumor Subpopulation Spatial Analysis</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Hyunji Lee, Gyumin Park (GIST, Prof. Jihwan Park)
                            &middot; Topic: Cell-cell interaction at tumor periphery
                        </p>
                        <p class="text-gray-700 mb-4">
                            Analyzed the P5 CRC (colorectal cancer) dataset to identify transcriptionally and spatially distinct tumor subpopulations.
                            Subclustered tumor cells into four populations (C0, C1, C2, C4) using Seurat, mapped their spatial distributions with kernel density estimation,
                            and defined tumor periphery regions. Cell type proportions at the tumor periphery were quantified, revealing high CAF and endothelial presence.
                            CellChat was used to identify incoming and outgoing cell-cell interaction signals for each tumor subcluster, uncovering
                            subcluster-specific communication patterns between tumor and non-tumor cells.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/1st/team5_img6.png" alt="Feature plots of marker genes" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Marker gene feature plots (IGKC, COL3A1, DCN, SPARC)</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/1st/team5_img8.png" alt="Cell type proportion heatmap at tumor periphery" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Cell type proportion at tumor periphery per subcluster</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 6: Geninus-SKKU -->
                    <div id="geninus-skku" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Visium HD and Xenium Integration</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Heesoo Kim, Kyuran Lee, Doeon Gu, Yeonju Lee (Geninus &amp; SKKU)
                            &middot; Topic: Cell segmentation &amp; integration of high-resolution ST data
                        </p>
                        <p class="text-gray-700 mb-4">
                            Integrated Visium HD (whole transcriptome, 18k genes) with Xenium In Situ (422 genes, single-cell resolution)
                            to achieve both whole-transcriptome coverage and single-cell resolution.
                            Developed a workflow involving image alignment via affine matrix transformation, nuclei and boundary segmentation of Visium HD,
                            canonical marker-based Xenium annotation, and deconvolution at multiple bin levels (8&micro;m, 16&micro;m, nuclei, boundary).
                            Boundary segmentation achieved the highest single-cell matching rate (87.6%), outperforming all other binning strategies.
                            Proposed a location-based integration approach for combining modalities.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/1st/team6_img2.png" alt="Xenium and Visium HD comparison" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Xenium In Situ vs Visium HD platforms</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/1st/team6_img4.png" alt="Integration workflow" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Post-Xenium multimodal applications</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 8: PNU Colab -->
                    <div id="pnu" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Fast and Scalable SSAM</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            PNU Colab
                            &middot; Topic: Visium HD normalization &amp; unsupervised spatial classification
                        </p>
                        <p class="text-gray-700 mb-4">
                            Addressed normalization challenges in Visium HD data, identifying striped artifacts and bin-size gradients in raw counts.
                            Proposed two normalization strategies: (1) Bin2cell-style quantile normalization per row/column with sum normalization,
                            and (2) average convolution using PyTorch with kernel-based local smoothing.
                            For unsupervised spatial domain classification, developed an Adversarial Autoencoder Classifier (AAEC) that
                            performs categorical classification of pixels in latent space. Compared AAEC results against BANKSY and Bin2Cell,
                            demonstrating competitive spatial domain identification with k=7 clusters on the CRC dataset.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/1st/team8_img24.png" alt="AAEC classified spatial domains" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">AAEC spatial domain classification (k=7)</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/1st/team8_img30.png" alt="AAEC vs BANKSY comparison" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">AAEC vs BANKSY classification comparison</figcaption>
                            </figure>
                        </div>
                    </div>

                    <hr class="border-gray-200" />

                    <!-- Team 9: KRIBB-KOBIC -->
                    <div id="kribb" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Spatial Embedding of scRNA-seq Data</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Jiin Choi, Donggon Cha (KRIBB-KOBIC)
                            &middot; Topic: Integration of scRNA-seq with spatial coordinates
                        </p>
                        <p class="text-gray-700 mb-4">
                            Developed a k-NN-based method for embedding scRNA-seq data onto spatial coordinates using reference spatial transcriptomics data.
                            The approach finds k nearest neighbors of each single cell in the ST reference and averages their xy coordinates for spatial mapping.
                            Validated with a pilot study on mouse brain data (Visium V2 + Chromium), where cell type identity was successfully transferred
                            (e.g., Oligodendrocytes spatially co-localized). Applied to Visium HD P5 CRC dataset (281k cells) with bin2cell segmentation,
                            embedding ~9k single-cell Flex cells onto the spatial map and evaluating identity transfer accuracy via confusion matrices.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/1st/team9_img1.png" alt="Mouse brain Visium V2 spatial reference" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Pilot: mouse brain Visium V2 spatial reference</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/1st/team9_img3.png" alt="Embedded scRNA-seq cells on spatial map" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">Embedding result via 3-NN coordinate averaging</figcaption>
                            </figure>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Single-cell Transcriptomics Track -->
            <section>
                <h3 class="text-2xl font-bold mb-6 pb-2 border-b-2 border-blue-600">Single-cell Transcriptomics</h3>
                <div class="space-y-10">

                    <!-- Team 2: IBS -->
                    <div id="ibs" class="scroll-mt-4">
                        <h4 class="text-xl font-semibold mb-1">Biological Batch Resilient Gene Selection (BarGS)</h4>
                        <p class="text-sm text-gray-500 mb-3">
                            Ohbin Kwon, Youngchul Oh (IBS Center for Genome Engineering, P.I. Heetak Lee)
                            &middot; Topic: Sane method for HVG selection
                        </p>
                        <p class="text-gray-700 mb-4">
                            Proposed BarGS, a method to filter out batch-effect-driving genes from highly variable gene (HVG) lists in scRNA-seq data.
                            Standard HVG selection (e.g., Seurat VST) captures biological signal but also includes genes driven by biological batch effects
                            (genotype, treatment), which confound downstream clustering. BarGS identifies DEGs between biological batches via pseudo-bulking
                            with DESeq2, removes them from HVGs, then rescues potential marker genes using an entropy-based significance test.
                            Tested on a gastric organoid dataset (RNF43/ZNRF3 loss &plusmn; KrasG12D), showing improved UMAP separation of cell types
                            after removing 556 batch-effect DEGs and rescuing 22 entropy-significant marker genes.
                        </p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <figure>
                                <img src="/results/1st/team2_img9.png" alt="Venn diagram of HVG vs DEG overlap" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">HVG vs DEG overlap (556 shared genes removed)</figcaption>
                            </figure>
                            <figure>
                                <img src="/results/1st/team2_img8.png" alt="UMAP after removing batch-effect DEGs" class="rounded-lg w-full" />
                                <figcaption class="text-sm text-gray-500 mt-1 text-center">UMAP after removing batch-effect DEGs</figcaption>
                            </figure>
                        </div>
                    </div>

                </div>
            </section>
        </div>
    </div>
</div>
