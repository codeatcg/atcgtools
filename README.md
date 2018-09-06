# atcgtools

1. The program is convenient for compare two vcf file with different formats by different methods.

The folder include two executable file vcfcompare and vcfcompare.exe.vcfcompare is for linux-64bit and vcfcompare.exe is for windows.
vcfcompare can read gzip compressed vcf files but vcfcompare.exe can't read that at present.

2. USAGE:
   
        vcfcompare <command> [options]\n
        DosageCor       calculate dosage correlation for each snp(commonly for imputed vcf files)\n
        IdosageCor      calculate dosage correlation for individual(for imputed vcf files)\n
        DsgtCor calculate corelation between dosage and genotype by different methods for each snp\n
        IdsgtCor        calculate corelation between dosage and genotype by different methods for individual\n
        GtgtCor calculate corelation between genotype and genotype by different methods for each snp\n
        IgtgtCor        calculate corelation between genotype and genotype by different methods for individual\n
        Split   split vcf file by chromosome\n
        Note: The program compare two vcf files by chromosome and the snps must be ordered by physical position.If the ordered vcf file include more than one chromosome please use the split command first\n

(1) DosageCor and IdosageCor have the same parameters\n
    --indpair:      the pair to be compaired\n
    --f1:   file1 to be compaired,corresponding to the first column of pair file\n
    --f2:   file2 to be compaired,corresponding to the second column of pair file\n
    --out:  output file\n
    
(2) DsgtCor, IdsgtCor, GtgtCor and IgtgtCor have the same parameters\n
    --indpair:      the pair to be compaired\n
    --f1:   file1 to be compaired,corresponding to the first column of pair file\n
    --f2:   file2 to be compaired,corresponding to the second column of pair file\n
    --DP1:  low depth[int]\n
    --DP2:  high depth[int]\n
    --GQ:   quality[int]\n
    --miss: missing rate[float]\n
    --method:\n
                    1 ref code 0 and alt code 2\n
                    2 maf code 2 and alt code 0\n
                    3 probability\n
                    4 file2 with no DP GQ,ref code 0 and alt code 2\n
                    5 file2 with no DP GQ,maf code 2 and alt code 0\n
    --out:  output file\n
    
(3) Split\n
    --in <vcf file> --out <output directory>\n
