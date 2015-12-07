# VCF Specifications

VCF is a text file format. It contains meta-information lines (prefixed with ”##”), a header line (prefixed with ”#”), and data lines each containing information about a position in the genome and genotype information on samples for each position (text fields separated by tabs). Zero length fields are not allowed, a dot (”.”) should be used instead. In order to ensure interoperability across platforms, VCF compliant implementations must support both LF (\n) and CR+LF (\r\n) newline conventions. [VCFv4.3]

In the FHIR-Genomics:

1. VCF reader: Using vcf module or pyvcf. Currently, we chose the Reader in vcf.
2. In load_example.py we add the method of load_vcf_example(vcf_file) to implement loading data to the database.
3. Meanwhile we defined a new source type: Sequencevcf to avoid conflicts (for example: in models.py) with previous type definition.
4. The type of VCF data is different from the previous sequence_resource declared in Sequence.py, therefore, we added a new resouce type: sequencevcf_resource.
5. Example file store path: fhir/example/vcf/filename
6. Since there are few modifications among VCF versions, temporarily we use examples in VCFv4.1.
