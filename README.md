# cDNA_converter
Convert DNA coordinate & transcript ID to cDNA coordinate

# Instructions 

1. Run `create_converter_from_gtf`. If you want to use annotation file other than ensembl v108 you will have to replace the file in the `gtf/` folder. And you can comment out the if condition in the first chunk which downloads the ensembl v108 gtf file.
2. Pop your input file which contains essential columns `tx_id` and `genomic_coordinate` into `input_file/`
3. Run `convert_to_cdna.Rmd`. output will be saved  `output_file/` 

# Scripts 

##### `create_converter_from_gtf.Rmd`
- this takes a transcript annotation GTF file and adds columns which will allow us to easily convert between genomic coordinate and cDNA coordinate. 
- Right now it downloads ensembl v108 transcripts into `gtf/` and adds columns to this file, but it can easily be changed to add the columns to any file in gtf format (just change the input file)

##### `convert_to_cdna.Rmd`
- this does the actual genomic coordinate -> cDNA position conversion. 
- Required columns in the file you want to convert are just `transcript_id` and `genomic_coordinate`
- It can have any other columns as well, just requires those 3 columns to work
- uses a data.table join so is quick! <3 data.table
