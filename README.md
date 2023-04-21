# Lab-Notebook
for GEN711

git clone https://github.com/atrott811/Lab-Notebook.git
# pulls linked item

github.com/jthmiller/gen711-811-example

fork the repositories (jthmiller and group repositories)

we did some changes with the groups main repositories for group leader to merge

4/21
created trimmed_fast.q directory
activate conda environment
git add <-- would add to file if permission wasn't denied
git commit -m

cp /tmp/gen711_project_data/fastp-single.sh ~/fastp-single.sh
chmod +x ~/fastp-single.sh
./fastp-single.sh 150 /tmp/gen711_project_data/FMT/fastqs  trimmed_fast.q/
conda activate qiime2-2022.8

qiime tools import \
   --type "SampleData[PairedEndSequencesWithQuality]"  \
   --input-format CasavaOneEightSingleLanePerSampleDirFmt \
   --input-path /home/users/apt1019/trimmed_fast.q \
   --output-path /home/users/apt1019/trimmed_fast.q/trimmed_fastq.qiimed\

   qiime cutadapt trim-paired \
    --i-demultiplexed-sequences /home/users/apt1019/trimmed_fast.q/trimmed_fastq.qiimed \
    --p-cores 4 \
    --p-front-f TACGTATGGTGCA \
    --p-discard-untrimmed \
    --p-match-adapter-wildcards \
    --verbose \
    --o-trimmed-sequences /home/users/apt1019/trimmed_fast.q/trimmed_fastq.qza

    qiime demux summarize \
--i-data /home/users/apt1019/trimmed_fast.q//trimmed_fastq.qza \
--o-visualization  /home/users/apt1019/trimmed_fast.q/trimmed_fastq.qzv 
