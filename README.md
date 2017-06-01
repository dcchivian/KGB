<A NAME="top"></A>
# KGB

  The KGB Genome Browser
 
  An IPython/Jupyter Notebook genome browser that enables comparative
  browsing and searching of genome contig assemblies, with additional
  support for

  * domain structure visualization
  * gene homology
  * phylogenetic trees
   

<br><br>
![KBase logo](https://avatars2.githubusercontent.com/u/1263946?v=3&s=84 "KBase") Designed to work with the DOE Systems Biology Knowledgebase (KBase)  (or in any Jupyter notebook with Genbank files)


### Contents
 - [Genome View Mode](#genome_mode)
 - [Homologs View Mode](#homologs_mode)
 - [Tree View Mode](#tree_mode)
 - [Contigs View Mode](#contigs_mode)
 - [Search](#search)
 - [Local Jupyter Notebook Example with NCBI annotated genomes](#example_1)
 - [KBase Narrative Example with KBase annotated genomes](#example_2)


<br><br>
<A NAME="genome_mode"></A>
### Genome View Mode
![KGB Genome Mode](https://raw.github.com/dcchivian/KGB/master/img/KGB_example_1_genome_mode.png "KGB Genome Mode")

Genome Mode shows only the primary Contig.  Navigation can be accomplished by clicking on the "circle" representation of the Contig.

#### Configuration


[\[back to top\]](#top)



<br><br>
<A NAME="homologs_mode"></A>
### Homologs View Mode
![KGB Homologs Mode](https://raw.github.com/dcchivian/KGB/master/img/KGB_example_1_homologs_mode.png "KGB Homologs Mode")


[\[back to top\]](#top)



<br><br>
<A NAME="tree_mode"></A>
### Tree View Mode
![KGB Tree Mode](https://raw.github.com/dcchivian/KGB/master/img/KGB_example_1_tree_mode.png "KGB Tree Mode")

[\[back to top\]](#top)



<br><br>
<A NAME="contigs_mode"></A>
### Contigs View Mode
![KGB Contigs Mode](https://raw.github.com/dcchivian/KGB/master/img/KGB_example_1_contigs_mode.png "KGB Contigs Mode")

[\[back to top\]](#top)



<br><br>
<A NAME="search"></A>
### Search

Search terms that scan functional annotations and gene names may be configured prior to invoking KGB.  Each term is assigned a color and marked on the contig navigation, allowing for jumping to that position in the genome.

```
Search_Terms = ['dna-directed polymerase',
	       '16S',
	       'DNA and methyltransferase',
	       '1.10.3.-',
	       'fucI',
	       'sulfate adenylyl transferase']
```

[\[back to top\]](#top)



<br><br>
<A NAME="example_1"></A>
### Local Jupyter Notebook Example with NCBI annotated Genomes

```
%pylab notebook  # must occur prior to invoking KGB if running KGB as an exec()
KBase_backend = False

GenomeSet_names = ["Gsulf", "DvulH", "DdesulfG20", "EcoliK12", "Bsub", "DaudaxMP104C"]
ContigSet_names = []
PivotFeatures_IDs = ["GSU2863", "DVU2928", "Dde_2997", "b3987", "BSU01070", "Daud0216"]
PrimaryAnchor_leafId = "Gsulf rpoB"
PrimaryAnchor_locusTag = "GSU2863"

genome_annotation_system = 'NCBI'
genome_data_format = "Genbank"
# if relative path to scaffolds is e.g.: ./data_example/NCBI_annot/genomes/Gsulf/scaffolds/scaf_1.gbk
gbk_ext = "gbk"
genome_data_base_path = "./data_example/NCBI_annot/genomes"
genome_data_extra_subpath = "/scaffolds"

domain_data_exists = False  # NCBI annotated genome
domain_data_format = None
domain_data_base_path = None
domain_data_extra_subpath = None
domain_family_desc_base_path = None

tree_data_format = 'newick'
# if relative path to tree is e.g.: ../data_example/NCBI_annot/trees/rpoB_tree-names.newick
tree_data_base_path = './data_example/NCBI_annot/trees'
tree_data_file = 'rpoB_tree-names.newick'

Search_Terms = ['dna-directed polymerase',
                '16S',
                'DNA and methyltransferase',
                '1.10.3.-',
                'fucI',
                'sulfate adenylyl transferase']

# run KGB
from urllib.request import urlopen
import_code = urlopen('https://raw.githubusercontent.com/dcchivian/KGB/master/KGB.py')
exec(import_code.read())
```

[\[back to top\]](#top)


<br><br>
<A NAME="example_2"></A>
### KBase Narrative Example with KBase annotated genomes

This functionality is currently disabled.  It will be back shortly.  Feel free to remind me to fix it! :-)

[\[back to top\]](#top)



<br><br><br><br>
Copyright 2015-2017 Dylan Chivian
