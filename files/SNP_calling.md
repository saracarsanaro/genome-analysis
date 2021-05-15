## Produce a VCF of SNPs from a FASTQ

### FASTQ to VCF - SNP calling
1. FASTQC
2. FASTQGroomer
3. Trimmomatic
4. FASTQC
5. BWA or Bowtie2 HISAT
6. FreeBayes
7. VCFfilter
8. VCFannotate - intersect VCF with BED annotations

### Galaxy Workflow
```json
{
    "a_galaxy_workflow": "true",
    "annotation": "",
    "format-version": "0.1",
    "name": "Unit10_4_Workflow",
    "steps": {
        "0": {
            "annotation": "",
            "content_id": null,
            "errors": null,
            "id": 0,
            "input_connections": {},
            "inputs": [
                {
                    "description": "",
                    "name": "HW5_Part2_sample_NGS_data.fq.gz"
                }
            ],
            "label": "HW5_Part2_sample_NGS_data.fq.gz",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "left": 10,
                "top": 10
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "92631bf6-0c05-49df-a378-c866d7e8ed28",
            "workflow_outputs": []
        },
        "1": {
            "annotation": "",
            "content_id": null,
            "errors": null,
            "id": 1,
            "input_connections": {},
            "inputs": [
                {
                    "description": "",
                    "name": "sang_Part2_sample_NGS_data.fq.gz"
                }
            ],
            "label": "sang_Part2_sample_NGS_data.fq.gz",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "left": 10,
                "top": 130
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "f91f9649-595b-40fb-9e7c-4cf63ad22dad",
            "workflow_outputs": []
        },
        "2": {
            "annotation": "",
            "content_id": null,
            "errors": null,
            "id": 2,
            "input_connections": {},
            "inputs": [
                {
                    "description": "",
                    "name": "sanggz_sample_NGS_data.fq.gz"
                }
            ],
            "label": "sanggz_sample_NGS_data.fq.gz",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "left": 10,
                "top": 250
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "d1a96f2d-af08-47d3-b3a7-da3989ac803b",
            "workflow_outputs": []
        },
        "3": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 3,
            "input_connections": {
                "input_file": {
                    "id": 0,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "FastQC",
            "outputs": [
                {
                    "name": "html_file",
                    "type": "html"
                },
                {
                    "name": "text_file",
                    "type": "txt"
                }
            ],
            "position": {
                "left": 230,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastq\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/hg19.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "03ebf215-6f93-431a-9e1f-fcb16a032804",
            "workflow_outputs": []
        },
        "4": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 4,
            "input_connections": {
                "input_file": {
                    "id": 1,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "FastQC",
            "outputs": [
                {
                    "name": "html_file",
                    "type": "html"
                },
                {
                    "name": "text_file",
                    "type": "txt"
                }
            ],
            "position": {
                "left": 230,
                "top": 130
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastq\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/hg19.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "fd493169-eafa-4de9-ac84-2b774ea477db",
            "workflow_outputs": []
        },
        "5": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "errors": null,
            "id": 5,
            "input_connections": {
                "readtype|fastq_r1_in": {
                    "id": 0,
                    "output_name": "output"
                },
                "readtype|fastq_r2_in": {
                    "id": 1,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Trimmomatic",
            "outputs": [
                {
                    "name": "fastq_out_r1_paired",
                    "type": "input"
                },
                {
                    "name": "fastq_out_r2_paired",
                    "type": "input"
                },
                {
                    "name": "fastq_out_r1_unpaired",
                    "type": "input"
                },
                {
                    "name": "fastq_out_r2_unpaired",
                    "type": "input"
                }
            ],
            "position": {
                "left": 230,
                "top": 250
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "tool_shed_repository": {
                "changeset_revision": "898b67846b47",
                "name": "trimmomatic",
                "owner": "pjbriggs",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/hg19.len\", \"illuminaclip\": {\"do_illuminaclip\": \"false\", \"__current_case__\": 1}, \"operations\": [{\"__index__\": 0, \"operation\": {\"name\": \"SLIDINGWINDOW\", \"__current_case__\": 0, \"window_size\": \"4\", \"required_quality\": \"20\"}}], \"output_err\": \"false\", \"output_logs\": \"false\", \"readtype\": {\"single_or_paired\": \"pair_of_files\", \"__current_case__\": 1, \"fastq_r1_in\": null, \"fastq_r2_in\": null}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.38.0",
            "type": "tool",
            "uuid": "2cd5dc26-762c-462c-a974-e375cc59fe40",
            "workflow_outputs": []
        },
        "6": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 6,
            "input_connections": {
                "input_file": {
                    "id": 5,
                    "output_name": "fastq_out_r2_paired"
                }
            },
            "inputs": [],
            "label": null,
            "name": "FastQC",
            "outputs": [
                {
                    "name": "html_file",
                    "type": "html"
                },
                {
                    "name": "text_file",
                    "type": "txt"
                }
            ],
            "position": {
                "left": 450,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/hg19.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "684fc14f-017d-4700-8604-3f495d76dc1e",
            "workflow_outputs": []
        },
        "7": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 7,
            "input_connections": {
                "input_file": {
                    "id": 5,
                    "output_name": "fastq_out_r1_paired"
                }
            },
            "inputs": [],
            "label": null,
            "name": "FastQC",
            "outputs": [
                {
                    "name": "html_file",
                    "type": "html"
                },
                {
                    "name": "text_file",
                    "type": "txt"
                }
            ],
            "position": {
                "left": 450,
                "top": 130
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/hg19.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "31e6b5eb-8125-421b-8476-ee8a436c78ee",
            "workflow_outputs": []
        },
        "8": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/bwa/bwa/0.7.17.4",
            "errors": null,
            "id": 8,
            "input_connections": {
                "input_type|fastq_input1": {
                    "id": 5,
                    "output_name": "fastq_out_r1_paired"
                },
                "input_type|fastq_input2": {
                    "id": 5,
                    "output_name": "fastq_out_r2_paired"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Map with BWA",
            "outputs": [
                {
                    "name": "bam_output",
                    "type": "bam"
                }
            ],
            "position": {
                "left": 450,
                "top": 250
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/bwa/bwa/0.7.17.4",
            "tool_shed_repository": {
                "changeset_revision": "3fe632431b68",
                "name": "bwa",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"analysis_type\": {\"analysis_type_selector\": \"illumina\", \"__current_case__\": 0}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/hg19.len\", \"input_type\": {\"input_type_selector\": \"paired\", \"__current_case__\": 0, \"fastq_input1\": null, \"fastq_input2\": null, \"adv_pe_options\": {\"adv_pe_options_selector\": \"do_not_set\", \"__current_case__\": 1}}, \"reference_source\": {\"reference_source_selector\": \"cached\", \"__current_case__\": 0, \"ref_file\": \"hg19\"}, \"rg\": {\"rg_selector\": \"do_not_set\", \"__current_case__\": 3}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.7.17.4",
            "type": "tool",
            "uuid": "b6a4430d-512a-4335-bf66-9f43005ed490",
            "workflow_outputs": []
        },
        "9": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/freebayes/freebayes/1.3.1",
            "errors": null,
            "id": 9,
            "input_connections": {
                "reference_source|batchmode|input_bams": {
                    "id": 8,
                    "output_name": "bam_output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "FreeBayes",
            "outputs": [
                {
                    "name": "output_vcf",
                    "type": "vcf"
                }
            ],
            "position": {
                "left": 670,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/freebayes/freebayes/1.3.1",
            "tool_shed_repository": {
                "changeset_revision": "ef2c525bd8cd",
                "name": "freebayes",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/hg19.len\", \"coverage_options\": {\"coverage_options_selector\": \"do_not_set\", \"__current_case__\": 1}, \"options_type\": {\"options_type_selector\": \"simple\", \"__current_case__\": 1}, \"reference_source\": {\"reference_source_selector\": \"cached\", \"__current_case__\": 0, \"batchmode\": {\"processmode\": \"individual\", \"__current_case__\": 0, \"input_bams\": null}, \"ref_file\": \"hg19\"}, \"target_limit_type\": {\"target_limit_type_selector\": \"limit_by_region\", \"__current_case__\": 2, \"region_chromosome\": \"chr22\", \"region_start\": \"0\", \"region_end\": \"51304566\"}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.3.1",
            "type": "tool",
            "uuid": "50540a13-a268-4029-bec9-666b3ddeb054",
            "workflow_outputs": []
        },
        "10": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/vcffilter/vcffilter2/1.0.0_rc3+galaxy3",
            "errors": null,
            "id": 10,
            "input_connections": {
                "input1": {
                    "id": 9,
                    "output_name": "output_vcf"
                }
            },
            "inputs": [],
            "label": null,
            "name": "VCFfilter:",
            "outputs": [
                {
                    "name": "out_file1",
                    "type": "vcf"
                }
            ],
            "position": {
                "left": 890,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/vcffilter/vcffilter2/1.0.0_rc3+galaxy3",
            "tool_shed_repository": {
                "changeset_revision": "fa24bf0598f4",
                "name": "vcffilter",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"vcf\", \"allele_tag\": \"false\", \"append_filter\": \"false\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/hg19.len\", \"filter_repeat\": [{\"__index__\": 0, \"filter_type\": \"-f\", \"filter_value\": \"DP > 10\"}, {\"__index__\": 1, \"filter_type\": \"-f\", \"filter_value\": \"AF = 0.5\"}], \"filter_sites\": \"false\", \"input1\": null, \"invert\": \"false\", \"or\": \"false\", \"region\": \"\", \"tag_fail\": \"false\", \"tag_pass\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.0.0_rc3+galaxy3",
            "type": "tool",
            "uuid": "e8b03e1f-140f-4860-905f-b4cd2baaf39e",
            "workflow_outputs": []
        },
        "11": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/vcfannotate/vcfannotate/1.0.0_rc3+galaxy0",
            "errors": null,
            "id": 11,
            "input_connections": {
                "bed_data": {
                    "id": 2,
                    "output_name": "output"
                },
                "input": {
                    "id": 9,
                    "output_name": "output_vcf"
                }
            },
            "inputs": [],
            "label": null,
            "name": "VCFannotate:",
            "outputs": [
                {
                    "name": "out_file1",
                    "type": "vcf"
                }
            ],
            "position": {
                "left": 890,
                "top": 130
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/vcfannotate/vcfannotate/1.0.0_rc3+galaxy0",
            "tool_shed_repository": {
                "changeset_revision": "01e0321aca98",
                "name": "vcfannotate",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"vcf\", \"bed_data\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/hg19.len\", \"input\": null, \"key_option\": \"BED-features\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.0.0_rc3+galaxy0",
            "type": "tool",
            "uuid": "013ae8ce-368c-4a80-ab8d-eb6e82a89080",
            "workflow_outputs": []
        },
        "12": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/vcfannotate/vcfannotate/1.0.0_rc3+galaxy0",
            "errors": null,
            "id": 12,
            "input_connections": {
                "input": {
                    "id": 10,
                    "output_name": "out_file1"
                }
            },
            "inputs": [],
            "label": null,
            "name": "VCFannotate:",
            "outputs": [
                {
                    "name": "out_file1",
                    "type": "vcf"
                }
            ],
            "position": {
                "left": 1110,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/vcfannotate/vcfannotate/1.0.0_rc3+galaxy0",
            "tool_shed_repository": {
                "changeset_revision": "01e0321aca98",
                "name": "vcfannotate",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"vcf\", \"bed_data\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/hg19.len\", \"input\": null, \"key_option\": \"BED-features\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.0.0_rc3+galaxy0",
            "type": "tool",
            "uuid": "f5790ad3-1f45-4a30-8362-ac91d4f2b090",
            "workflow_outputs": []
        },
        "13": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/vcfannotate/vcfannotate/1.0.0_rc3+galaxy0",
            "errors": null,
            "id": 13,
            "input_connections": {
                "bed_data": {
                    "id": 2,
                    "output_name": "output"
                },
                "input": {
                    "id": 10,
                    "output_name": "out_file1"
                }
            },
            "inputs": [],
            "label": null,
            "name": "VCFannotate:",
            "outputs": [
                {
                    "name": "out_file1",
                    "type": "vcf"
                }
            ],
            "position": {
                "left": 1110,
                "top": 130
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/vcfannotate/vcfannotate/1.0.0_rc3+galaxy0",
            "tool_shed_repository": {
                "changeset_revision": "01e0321aca98",
                "name": "vcfannotate",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"vcf\", \"bed_data\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/hg19.len\", \"input\": null, \"key_option\": \"BED-features\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.0.0_rc3+galaxy0",
            "type": "tool",
            "uuid": "a8197beb-db39-496c-9940-bad4cbe36d51",
            "workflow_outputs": []
        }
    },
    "tags": [],
    "uuid": "77f69590-9fc3-4192-8d21-e019acbf005c",
    "version": 0
}
```
