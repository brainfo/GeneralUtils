# GeneralUtils
general bioinformatic jobs

This encompasses general and simple things you will face:
- download fastqs from EBI
- parallel jobs using python
- merge fastqs from different lanes
  What this util do:
  1. input the rawdir, with each sample a subfolder containing multiple lanes _1.fq.gz and _2.fq.gz
  2. automatically craete and output the outdir where each sample a subfolder containing one _1.fq.gz and one _2.fq.gz
  
  Example input structure:  
```
├── AZ_16wk_Adip_Lib
│   ├── AZ_16wk_Adip_Lib_MKDL240001394-1A_222TC7LT4_L3_1.fq.gz
│   ├── AZ_16wk_Adip_Lib_MKDL240001394-1A_222TC7LT4_L3_2.fq.gz
│   ├── AZ_16wk_Adip_Lib_MKDL240001394-1A_222TJNLT4_L3_1.fq.gz
│   ├── AZ_16wk_Adip_Lib_MKDL240001394-1A_222TJNLT4_L3_2.fq.gz
│   ├── AZ_16wk_Adip_Lib_MKDL240001394-1A_22K2MLLT3_L4_1.fq.gz
│   ├── AZ_16wk_Adip_Lib_MKDL240001394-1A_22K2MLLT3_L4_2.fq.gz
│   └── MD5.txt
├── AZ_52wk_Adip_Lib
│   ├── AZ_52wk_Adip_Lib_MKDL240001396-1A_222TJNLT4_L3_1.fq.gz
│   ├── AZ_52wk_Adip_Lib_MKDL240001396-1A_222TJNLT4_L3_2.fq.gz
│   ├── AZ_52wk_Adip_Lib_MKDL240001396-1A_227K77LT4_L2_1.fq.gz
│   ├── AZ_52wk_Adip_Lib_MKDL240001396-1A_227K77LT4_L2_2.fq.gz
│   ├── AZ_52wk_Adip_Lib_MKDL240001396-1A_22K2KWLT3_L1_1.fq.gz
│   ├── AZ_52wk_Adip_Lib_MKDL240001396-1A_22K2KWLT3_L1_2.fq.gz
│   └── MD5.txt
└── VZ_36wk_Adip_Lib
    ├── MD5.txt
    ├── VZ_36wk_Adip_Lib_MKDL240001395-1A_222TC7LT4_L3_1.fq.gz
    ├── VZ_36wk_Adip_Lib_MKDL240001395-1A_222TC7LT4_L3_2.fq.gz
    ├── VZ_36wk_Adip_Lib_MKDL240001395-1A_222TJNLT4_L8_1.fq.gz
    ├── VZ_36wk_Adip_Lib_MKDL240001395-1A_222TJNLT4_L8_2.fq.gz
    ├── VZ_36wk_Adip_Lib_MKDL240001395-1A_22K2MLLT3_L4_1.fq.gz
    └── VZ_36wk_Adip_Lib_MKDL240001395-1A_22K2MLLT3_L4_2.fq.gz

3 directories, 21 files
```

  Example output structure:  
```
├── AZ_16wk_Adip_Lib
│   ├── AZ_16wk_Adip_Lib_merge_1.fq.gz
│   └── AZ_16wk_Adip_Lib_merge_2.fq.gz
├── AZ_52wk_Adip_Lib
│   ├── AZ_52wk_Adip_Lib_merge_1.fq.gz
│   └── AZ_52wk_Adip_Lib_merge_2.fq.gz
└── VZ_36wk_Adip_Lib
    ├── VZ_36wk_Adip_Lib_merge_1.fq.gz
    └── VZ_36wk_Adip_Lib_merge_2.fq.gz
```

  What you do:
  1. clone this repo
  2. inside the cloned local folder, run `python merge_fqs.py -n 1 -i ${rawdir} -o ${outdir}`
- ... Maybe rename samples with matched name information
