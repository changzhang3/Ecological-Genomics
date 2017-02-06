# Project title    

## Author: Chang Zhang 
    
### Ecological Genomics:   

## Overall Description of notebook      

fill in your description here!


## Date started: (2017-01-18)   
## Date end:   (year-month-day)    

## Philosophy   
Science should be reproducible and one of the best ways to achieve this is by logging research activities in a notebook. Because science/biology has increasingly become computational, it is easier to document computational projects in an electronic form, which can be shared online through Github.    

### Helpful features of the notebook     

**It is absolutely critical for your future self and others to follow your work.**     

* The notebook is set up with a series of internal links from the table of contents.    
* All notebooks should have a table of contents which has the "Page", date, and title (information that allows the reader to understand your work).     
* Also, one of the perks of keeping all activities in a single document is that you can **search and find elements quickly**.     
* You can document anything you'd like, aside from logging your research activities. For example:
	* feel free to log all/any ideas for your research project([example](https://github.com/adnguyen/Notebooks_and_Protocols/blob/master/2016_notebook.md#page-39-2016-06-13-post-doc-project-idea-assessing-current-impacts-of-climate-change-in-natural-populations)) as an entry,     
	* or write down notes for a paper([example](https://github.com/adnguyen/Notebooks_and_Protocols/blob/master/2016_notebook.md#id-section36).      

* Lastly, you can share specific entries because of the three "#" automatically creates a link when the notebook renders on github.      


### Table of contents for 60 entries (Format is *Page: Date(with year-month-day). Title*)

## 2017-01-23

# Info update
* outline
* 20 min
* learning.engaging activity
* use board 
* take home messages
* examples from literature

* advances in sequencing tech
* range of applications: WGS, RNAseq, ChIPseq, targeted/capture seq (custom-designed probes)
	* reducing representation:
		* Use RNA (will be concentrated at highly expressed genes, such as actin)
		* GBS/RAD-seq
	* Illumina is generating 90% of global data
* library prep: depends on the application
	* extract DNA or RNA (cDNA synthesis)
	* fragment sample, size selection
	* ligate adapters
		* individual barcode
	* add on sequencing adapters
	* PCR
* Sequencing-by-Synthesis (SBS)
	* DNA with adapters get loaded onto a lane on a flow cell
	* DNA washed over the lane and attached to the oligos
	* bridge amplification -- cluster generation
	* incorporate labeled dNTP -- imaging and recording which nucleotide is added
* other technologies
	* PacBio
		* Single molecule, Real time
		* 10,000- 60,000bp
		* not as accurate
		* can be used for "haplotyping"
		* error rate 15%
* learning activity

Human genome project 
* Sanger (2001-2003) vs. Hiseq (2014)
	* 15 yr vs 1 day, 1 genome vs 45, $3 billion vs $1000

Choosing platforms:
* where is genetic variation, phenotypes of interest
* population vs individuals, comparative studies
* model organisms or not -- whether there is genetic information available
	* combining different approaches
	* de novo assembly for non-model
* demographic history
* Adaptive genetic variation
* gene expression variation

* length of reads
	* longer you have, assembly is easier, confidence is higher
* number of reads
* distribution
	* random or concentrated in an area?
	

Paper Discussion
* Ellegern et al. 

	We talked about:
	* reference genome
	
	
## 2017-01-25 

outline
* announcement
* info update: QTN
* debate
* discussion of group projects

# info update
* What are QTN?
	* Quantitative trait nucleotides
		* traits under selection, adaptive traits
			* flowering time, flower color, thermal tolerance, defense compounds, drought tolerance, toxin tolerance, venom potency, hypoxia tolerance...
			* Mendelian -> single gene locus
			* quantitative trait -> 
* Quantitative genetic theory of adaptive traits
* Methods
	* linkage mapping
	* GWAS
	* selection scans
	
Melissa's data
* sea star
* affect many different sea star species, can happen quickly

what is causing the disease? pathogen unknown

* symptoms: loss of turgor, lesion hole, limbs pulling off, turn into white glue and die at the end
* Use infected sea star to infect healthy ones for experiment
* Pisaster ochraceus -- bring in lab. 
* Densovirus implicated: Hewson et al. 2014 PNAS


##2017-02-01
info update
* WGS
	* applications
	
	* prior considerations
		*reference genome available?
		
	* limitations
		* rapidly evolving genes
		* large gene families
		* polymorphic genes
		* paralogs
		* usually using 1 individual
		* it won't be 100% whole genome -- heterochromatin, highly repetitive
	
	* more considerations:
		* Illumina 150bp, SOLiD 50bp, Pacific Biosciences 5kb, Ion Torrent 500bp, Illumina Moleculo up to 10kb
		* genome size: K-mer approach to estimate genome size, or flowcytometry 
		* repeat content
		* error rate of sequencing
		* degree of genome duplications, polypoidy
	
	* methods
		* tissue type: avoid energetically active tissue such as muscle (lots of mitochondria dna), avoid gut/skin (DNA from other organisms)
		* quantity of DNA: 6 microgram to 1 milligram
		* library prep
			* single or pair-end, get short contigs
			* mate pair: long sequence reads (thousands of bp), for making scaffolds
		* need to have an idea of GC content, repeat abundance, duplicate reads
		* assemble genome, quality control (N50: 50% of sequence greater than the "middle" bp long of the contigs-- don't want really small reads..)
		* annotate, according to related organisms (ref genome)

* RNA-seq
	* Advantage: 
		* differential genome expression
		* allelic specific expression -- environmental responses, adaptation
		* Functional relevant subset of the genome
		* vs. microarray
	* limitations 
		* vs. proteomics
		* post-transcriptional modifications
		* spatial, temporal
		* strand specificity
	* sequencing platforms, error profiles, sequencing coverage: 
		* pyrosequencing from Roche -- incorrect homopolymer
		* Ion torrent
		* Illumina -- GC content matters
		
* Unix
	* log in using ssh czhang3@pbio381.uvm.edu
	* 24 cpu cores
	* 32 Gb RAM
	* 1 TB HD
	* to check who's on it: $ top, to quite just to type q
	* home directory, symbolized by ~/
	* pwd tells you where you are
	* to look at what's in there, use ll command
	* make a new folder called mydata, using mkdir command
	* move around: use cd command
	* copy and paste file: go into the folder project data, ll the content, find the sample file, cp file name destination
	* usage of / 
	* the head command to print first 10 lines of file
	* head -n 15 file name ->customize how many lines to look at
	* tail command to look at the last 10 lines of file
	* Will use head and tail command a lot! -> look at file without opening the whole thing
	* grep tool to search for a target query
	* use grep to search HH samples and pull them out: grep 'what you want to pull' >name of file want to print
	* grep 'HH' ssw_samples.txt >ssw_HHonly.txt
	* wild cards *
	* delete files: rm ->very dangerous
	* add safeguard: .bashrc (a hidden file)
	* ll -a list all hidden files
	* use command vim .bashrc
	* type i to insert
	* type: alias rm='rm -i' , which is ask me to confirm
	* then type :q! to overwrite
	
	
2017-02-06

RNA-Seq workflow

* Approach, Experimental design, Library Prep, Sequencing

* Receive data

* Computer/Server setup

* After receiving fastq files
	* Evaluate quality
	
	* Clean reads (.fastq, .fq, .gzip)
		* adapters
		* nucleotide quality
		* length of reads
		
	* Evaluate Quality
	
	* de novo transcriptome Assembly (making the reference genome) (.fasta)
	
		* Evaluate assembly
		 * compare to closely related species
		 * compare to KEG/CEG (core eukaryotic genes) -- BlastX, get GO terms
		 * N50
		 * number of contigs
		 
		* Annotation (Blast)
	
	* Map reads to reference transcriptome (.sam, sequence alignment file)
	 * generates lots of alignment files
	  * each sample has an alignment file
	
	* a. Extract read count info (number of reads that map to each contig for each sample)
	* b. Identify SNPs
	
	* a. DGE analysis (Differential gene expression); Co-expression network analysis
	* b. Population genomics (genetic differentiation between groups, population structure, demographic history, test for signature of selection, etc.)
	
	
* Paper Discussion
 * unigenes: collapse splice varient contigs, typically the longest
 * example: 60 K unigenes, 10% cuticular HC, 2K DGE, 20% cuticular HC
	* all: 10%
	* DEG 20%, -> overrepresented
	

* RNA-Seq data analysis coding session

	* 1. go into the fastq file in /data/project_data/fastq using cd command
			cd /data/project_data/fastq
	* 2. each fastq file is in .gz, and has two files R1, R2 (R1 left reads, R2 right reads), 0-5 is disease scale (5 dead)
	
	* 3. file to work: 10_5-20_S_2_R1.fq.gz, 10_5-20_S_2_R2.fq.gz
		for evaluating, cleaning, and evaluating again
		* use zcat to look into zip file
			zcat 10_5-20_S_2_R1.fq.gz | head
			* looking at the fastq file: 4 lines of text per read
			 4th line: letters are Q-scores, aligned with every single nt
			  -> letters are good
			* use FastQC
			located in /data/popgen/ directory
			copy the trim_example.sh into my home directory (~/scripts)
			* vim trim_example.sh
			* in trimmomaticPE
				* in vim, first hit i to change to insert mode
				* changed file name, added /data/project_data/fastq/cleanreads/cleanreads/
				* 2 input, 4 output, also .fq
				* to save in vim, first press esc, :w (save only), :wq (save and quite), :q (to quite)
				* all vim commands starts with :
				* has the illuminaclip file, so it will trim off adapters
				* also headcrop first 9 nt
				* min length 35
				
				
			* run script: bash trim_example.sh
			or ./trim_example.sh
			* results:
			Input Read Pairs: 16966813 Both Surviving: 14470376 (85.29%) Forward Only Surviving: 1830846 (10.79%) Reverse Only Surviving: 303879 (1.79%) Dropped: 361712 (2.13%)
			
			 


	









	
# Glossary
* Reads
	* short 50bp
	* long 100, 150, 300bp (Miseq), 10,000-60,000bp (SMRT)
	* single vs paired-end	
	

  