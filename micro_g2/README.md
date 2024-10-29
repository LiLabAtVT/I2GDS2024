## Pipeline for assembling short read sequence data
Project description: Preprocessing FASTQ files and assembling raw short-read sequencing data.

### 1. To perform adapter trimming and quality filtering using [fastp](https://doi.org/10.1093/bioinformatics/bty560)
The code is located in the following path: `code/`.
- `fastp.py` : Python script to handle raw FASTQ data and run fastp for adapter identification and quality control.
  - This script will look for the files in the specified directory, automatically identify adapters, trim adapters, and run QC.
  - Need to specify the path to locate `fastp` and change the input and output directories in `fastp.py` before use.
  - Need to download `fastp` at the [GitHub](https://github.com/OpenGene/fastp)
    
    ```
    wget http://opengene.org/fastp/fastp
    chmod a+x ./fastp
    ```
  - **Input**: FASTQ files (either single-end or paired-end)
    - for single-end data, specify read1 input by `-i` or `--in1`, and specify read1 output by `-o` or `--out1`.
    - for paired-end data, specify read2 input by `-I` or `--in2`, and specify read2 output by `-O` or `--out2`.
    - `fastp.py` in `code/` is written for single-end data, need to modify if your data is paired-end
  - **Expected output**: `_QC.fastq.gz` gzip-compressed file
  - Run the following to execute the code.
  - test to see if it works
    
    ```
    python3 fastp.py
    ```
