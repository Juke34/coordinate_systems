## The coordinate systems 

It exists 4 possible coordinate representations but only two are used in genomics:

 * 0-based half-open
 * 1-based fully closed

Let's dive into the coordinates systems complexity.

![](img/coord.png)

| <div style="width:250px"> Coordinate system </div>	| Range | Example | Size of the range	| Array indexing <br>in programming | Institute/DB/ <br>File Format | Comment | 
| --- | --- | --- | --- | --- | --- | --- |
| - 0-based, fully closed <br> - 0-base inclusive start, inclusive end <br> - [0,] | [<span style="color:#ED8528">start</span>, <span style="color:#ED8528">end</span>] | [<span style="color:#ED8528">1</span>,<span style="color:#ED8528">3</span>] = TGC | <span style="color:#ED8528">end</span> - <span style="color:#ED8528">start</span> + 1 | | | |
| - 0-based, half-open <br> - 0-base inclusive start, exclusive end <br> - [0,) | [<span style="color:#ED8528">start</span>, <span style="color:#ED8528">end</span>) | [<span style="color:#ED8528">1</span>,<span style="color:#ED8528">4</span>) = TGC | <span style="color:#ED8528">end</span> - <span style="color:#ED8528">start</span>  | Bash, C, C++, ksh, Go, Haskell, Java, JS, Perl, Python, PowerShell, Ruby, Rust, Scala | UCSC DB, Genebank DB, BED, BAM, BCFv2, PSL, ASN, BigBed, bedGraph, GA4GH; HML 1.0 | |
| - 1-based, fully closed <br> - 1-base inclusive start, inclusive end <br> - [1,] | [<span style="color:#DF6EB8">start</span>, <span style="color:#DF6EB8">end</span>] | [<span style="color:#DF6EB8">2</span>,<span style="color:#DF6EB8">4</span>] = TGC | <span style="color:#DF6EB8">end</span> - <span style="color:#DF6EB8">start</span> + 1 | AWK, COBOL, Fortran, Julia, Lua, MATLAB, R, sh, XPath/Xquery, zsh | Ensembl, UCSC genome browser, Genbank file, GFF, GTF, SAM, VCF, Wiggle, GenomicRanges, BLAST, GenBank/EMBL Feature Table, HGVS | /!\ when describing indel you must know if the insertion is before or after the position |
| - 1-based, half-open <br> - 1-base inclusive start, exclusive end <br> - [1,) | [<span style="color:#DF6EB8">start</span>, <span style="color:#DF6EB8">end</span>) | [<span style="color:#DF6EB8">2</span>,<span style="color:#DF6EB8">5</span>) = TGC | <span style="color:#DF6EB8">end</span> - <span style="color:#DF6EB8">start</span>  |

## Interval types

I like this visual explaining the interval types. Credits is from [UCSC Genome Browser Blog](https://genome-blog.soe.ucsc.edu/blog/2016/12/12/the-ucsc-genome-browser-coordinate-counting-systems/)

![](https://genome-blog.soe.ucsc.edu/blog/wp-content/uploads/2016/12/newInterval.png)