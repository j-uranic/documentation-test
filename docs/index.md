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

# Subject line

Content goes here.
