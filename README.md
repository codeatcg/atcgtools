# atcgtools

1. The program is convenient for compare two vcf file with different formats by different methods.

The folder include two executable file vcfcompare and vcfcompare.exe.vcfcompare is for linux-64bit and vcfcompare.exe is for windows.
vcfcompare can read gzip compressed vcf files but vcfcompare.exe can't read that at present.

2. USAGE:
   
   vcfcompare <command> [options]
        DosageCor       calculate dosage correlation for each snp(commonly for imputed vcf files)
        IdosageCor      calculate dosage correlation for individual(for imputed vcf files)
        DsgtCor calculate corelation between dosage and genotype by different methods for each snp
        IdsgtCor        calculate corelation between dosage and genotype by different methods for individual
        GtgtCor calculate corelation between genotype and genotype by different methods for each snp
        IgtgtCor        calculate corelation between genotype and genotype by different methods for individual
        Split   split vcf file by chromosome
        Note: The program compare two vcf files by chromosome and the snps must be ordered by physical position.If the ordered vcf file include more than one chromosome please use the split command first

(1) DosageCor and IdosageCor have the same parameters
    --indpair:      the pair to be compaired
    --f1:   file1 to be compaired,corresponding to the first column of pair file
    --f2:   file2 to be compaired,corresponding to the second column of pair file
    --out:  output file
    
(2) DsgtCor, IdsgtCor, GtgtCor and IgtgtCor have the same parameters
    --indpair:      the pair to be compaired
    --f1:   file1 to be compaired,corresponding to the first column of pair file
    --f2:   file2 to be compaired,corresponding to the second column of pair file
    --DP1:  low depth[int]
    --DP2:  high depth[int]
    --GQ:   quality[int]
    --miss: missing rate[float]
    --method:
                    1 ref code 0 and alt code 2
                    2 maf code 2 and alt code 0
                    3 probability
                    4 file2 with no DP GQ,ref code 0 and alt code 2
                    5 file2 with no DP GQ,maf code 2 and alt code 0
    --out:  output file
    
(3) Split
    --in <vcf file> --out <output directory>
    
    
    
    
    
    
