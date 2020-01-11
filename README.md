# vcfcompare

## Description:

         The program is designed to compare two vcf file with different formats by different methods and to evaluated the strategies of imputation.

         The folder include two executable file vcfcompare and vcfcompare.exe. vcfcompare is compiled in the 64-bit mode (linux) and vcfcompare.exe is 32-bit version for windows.
         vcfcompare can read gzip compressed vcf files but vcfcompare.exe can't read that.
         
## Version
         Version: 0.1.0beta
         
         Because of single precision float and lack of inspection the ouput may include some abnormal values. The new verison fixed the bugs and will be upload soon.
         
         
         
## USAGE:
   
        vcfcompare <command> [options]
        DosageCor       calculate dosage correlation for each snp(commonly for imputed vcf files)
        IdosageCor      calculate dosage correlation for individual(for imputed vcf files)
        DsgtCor         calculate corelation between dosage and genotype by different methods for each snp
        IdsgtCor        calculate corelation between dosage and genotype by different methods for individual
        GtgtCor         calculate corelation between genotype and genotype by different methods for each snp
        IgtgtCor        calculate corelation between genotype and genotype by different methods for individual
        Split           split vcf file by chromosome
        Note: The program compare two vcf files by chromosome and the snps must be ordered by physical position.If the ordered vcf file include more than one chromosome please use the split command first

         (1) DosageCor and IdosageCor have the same parameters
             --indpair:      the pair to be compaired
             --f1:   file1 to be compaired,corresponding to the first column of pair file
             --f2:   file2 to be compaired,corresponding to the second column of pair file
             --out:  output file
    
         (2) DsgtCor, IdsgtCor, GtgtCor and IgtgtCor have the same parameters
             --indpair:      the pair to be compaired\n
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
    
 FORMAT:
 
         input:
         
         --indpair
         A1 A2
         B1 B2
         ......
         A1,A2 and B1,B2 indicate the same individual with different names which correspond to the names in file1 and file2,respectively.
         
         output:
         
         #CHROM	POS	COR	MAF
         CHROM          chromosome.
         POS            physical position
         COR            correlation of snps in file1 and file2 which contain more than one individual.
         MAF            minimal allele frequency of snps in file1.
         
         #IND1	IND2	COR	COUNT
         IND1,IND2      individual 1 and individual 2 which indicate the same individual correspond to names in file1 and file2.
         COR            correlation of individual 1 and individual 2.
         COUNT          valid snp counts used to calculate individual correlation.
         
Repot bugs:

         If you have questions please email me.
         Email: miaozepu@genomics.cn
         
    
    
    
    
    
