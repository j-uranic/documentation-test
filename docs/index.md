# Spatial Transcriptomics - Visium
													
## Consumer-focused  
**1. Date (published):** 2022-05-16   
**2. Version (of this document):** v1.0  
**3. Authors:** James Webber, Katelyn Flowers, Bill Flynn  
**4. What is being measured?   
    a.	Tags<sup>1</sup>:** Single-cell resolution, sequencing, imaging, transcriptomics  
    **b. Descriptive (optional):** Technologies for capturing transcriptome-wide gene expression in a spatial setting.  
**5. What analytical activities will the assay be used for within HuBMAP?**  
    **a.	Tags<sup>1</sup>:** Map-Creation-for-Organs; Data Integration; General Characterization Assay  
    **b.	Descriptive (optional):** These datasets will be used as a scaffold to map reference cell types into a spatial context, and identify spatial patterns in gene expression.  
 **6. What type of human samples are needed or used?**  
    **a.	Tags<sup>1</sup>:** Fresh Frozen; FFPE  
    **b.	Descriptive (optional): ** The two Different technologies can process different sample types  
 **7. Commercial Product:** 10X Visium  
<sup>*1</sup> Include tags that can be normalized across assays, allowing for assay filtering. When possible, use structured  terminology (ontologies).*

## Assay Description
**Primary Reference [PMCIDs](https://pubmed.ncbi.nlm.nih.gov/):** 
PMID: 27365449 (Spatial Transcriptomics / Visium, no PMCID)

**Related:**
PMC6927209 (Slide-Seq)
PMC8606189 (Slide-Seq V2)
	PMC7736559 (DBiT-Seq)
	
### **Technology Overview**

10x Genomics Visium Spatial Gene Expression slides utilize spatially barcoded mRNA-binding oligonucleotides oriented on a slide to capture mRNA in fresh frozen tissue or mRNA probe pairs in FFPE tissue sections. In either case, tissue is permeabilized to release mRNA or mRNA probes which bind to capture probes on the slide, and reverse transcription occurs while the tissue is still in place, generating a cDNA library that incorporates complements of the spatial barcodes and preserves spatial information. Barcoded libraries are mapped back to a specific spot on the Capture Area. This gene expression data is subsequently layered over a high-resolution microscope image of the tissue section, making it possible to visualize the expression of any mRNA, or combination of mRNAs, within the morphology of the tissue in a spatially resolved manner.

### **Key Definitions**

**Visium Slide**  
Each Visium slide has 2 - 4 mapping areas (also known as “capture areas”) in which spatially barcoded capture oligos are deposited.  Each slide has a unique serial number that determines the exact layout of the mapping area barcodes and perimeter fiducial markings.

**Mapping area**  
Each mapping area (also known as a capture area) contains spatially barcoded capture oligos, arranged in spots. When a tissue section is laid down on a mapping area, mRNA or mRNA-hybridizing probes precipitate down from the tissue and are captured on these oligos.  The mapping area geometry is square, measuring between 6.5mm to 11mm on a side.  The number of spots per mapping area is at least 4,992.

**Spot**  
A spot is a collection of capture oligos that share the same spatial barcode (but different UMI barcodes) and a known set of x,y coordinates.  For the first generation Visium assays, these capture spots are circular with a typical diameter of 55um and are separated (center-to-center) by 100um horizontally and 110um vertically.

**Spatial Barcode**  
A unique 16bp nucleotide sequence with known x,y coordinates that ligates to mRNA molecules.  This should not be confused with the unique molecular identifier (UMI) barcode that is used to distinguish between unique molecules within the same spot.

**Tissue Permeabilization**  
For the Visium Fresh Frozen workflow, the tissue section must be permeabilized to allow mRNA to precipitate down to the Visium slide to be captured.  The amount of time a tissue is permeabilized is critical, as under-permeabilization leads to lower overall yield due to fewer available mRNA molecules, whereas over-permeabilization leads to lateral diffusion of mRNA which can distort or inhibit the assay’s ability to detect the spatial localization of those molecules.  A common phenotype of the latter is mRNA present in regions of the slide not covered by tissue.

## **Antibodies**  
* ~~*N/A*~~

Please see the HuBMAP standard [report for antibody validation](https://avr.hubmapconsortium.org/).

															
# Provider-focused

## Files and Directories

### **Directory structure**

---
Directory structure:
  - Directory Name:raw
    Level:0
    Required?:yes
    Description:This is the raw, unmodified files coming from the sequencer. FASTQ
  - Directory Name:img
    Level:0
    Required?:yes
    Description:This folder contains any OME-compatible TIFF files (brightfield, fluorescent) taken of the spatial transcriptomics mapping area prior to tissue digestion.
  - Directory Name:lab
    Level:1
    Required?:yes
    Description:Processed files produced by the lab that generated the data.
  - Directory Name:lab/processed
    Level:1.1
    Required?:yes
    Description:The output from the primary analysis pipeline.
  - Directory Name:hive
    Level:2
    Required?:yes
    Description:Processed files produced by HIVE using the spatial pipeline.
---

