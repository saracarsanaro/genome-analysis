## De Novo Transcriptome Reconstruction

### Workflow
1. FASTQC
2. Trimmomatic
3. FastQC
4. HISAT2
5. Stringtie for for transcript reconstruction
6. Stringtie-merge to combine redundant transcript structures across the four samples and the RefSeq reference
7. GFFCompare to annotate the transcripts 
8. FeatureCounts
9. DESeq2 for differential gene expression testing

### DESeq2 Graphical Summary Sample to Sample Distances
![STS](/STS_RNA.png)

### DESeq2 Graphical Summary PCA
![PCA](/PCA_RNA.png)

### Output in IGV
![IGV](/RNAseq_IGV.png)

### Galaxy Workflow
``` json
{
    "a_galaxy_workflow": "true",
    "annotation": "",
    "format-version": "0.1",
    "name": "homework12part2",
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
                    "name": "G1E_rep1_forward_read_%28SRR549355_1%29"
                }
            ],
            "label": "G1E_rep1_forward_read_%28SRR549355_1%29",
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
            "uuid": "56dec791-69c8-403f-9211-bdbae317591a",
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
                    "name": "G1E_rep1_reverse_read_%28SRR549355_2%29"
                }
            ],
            "label": "G1E_rep1_reverse_read_%28SRR549355_2%29",
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
            "uuid": "b63823ee-99a1-4143-9955-76f5e8b1173c",
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
                    "name": "G1E_rep2_forward_read_%28SRR549356_1%29"
                }
            ],
            "label": "G1E_rep2_forward_read_%28SRR549356_1%29",
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
            "uuid": "7598bceb-42c8-452c-ac58-b3d86666c083",
            "workflow_outputs": []
        },
        "3": {
            "annotation": "",
            "content_id": null,
            "errors": null,
            "id": 3,
            "input_connections": {},
            "inputs": [
                {
                    "description": "",
                    "name": "G1E_rep2_reverse_read_%28SRR549356_2%29"
                }
            ],
            "label": "G1E_rep2_reverse_read_%28SRR549356_2%29",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "left": 10,
                "top": 370
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "588b3353-55a8-4359-88f1-4a301341a6a7",
            "workflow_outputs": []
        },
        "4": {
            "annotation": "",
            "content_id": null,
            "errors": null,
            "id": 4,
            "input_connections": {},
            "inputs": [
                {
                    "description": "",
                    "name": "Megakaryocyte_rep1_forward_read_%28SRR549357_1%29"
                }
            ],
            "label": "Megakaryocyte_rep1_forward_read_%28SRR549357_1%29",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "left": 10,
                "top": 490
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "3a25e244-fb38-4da0-9a16-62f5933a48bd",
            "workflow_outputs": []
        },
        "5": {
            "annotation": "",
            "content_id": null,
            "errors": null,
            "id": 5,
            "input_connections": {},
            "inputs": [
                {
                    "description": "",
                    "name": "Megakaryocyte_rep1_reverse_read_%28SRR549357_2%29"
                }
            ],
            "label": "Megakaryocyte_rep1_reverse_read_%28SRR549357_2%29",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "left": 10,
                "top": 610
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "b3778c39-6a39-404e-84fe-f2930d7c0c4c",
            "workflow_outputs": []
        },
        "6": {
            "annotation": "",
            "content_id": null,
            "errors": null,
            "id": 6,
            "input_connections": {},
            "inputs": [
                {
                    "description": "",
                    "name": "Megakaryocyte_rep2_forward_read_%28SRR549358_1%29"
                }
            ],
            "label": "Megakaryocyte_rep2_forward_read_%28SRR549358_1%29",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "left": 10,
                "top": 730
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "b0923f6a-81ba-4222-9699-ae9b00a9488e",
            "workflow_outputs": []
        },
        "7": {
            "annotation": "",
            "content_id": null,
            "errors": null,
            "id": 7,
            "input_connections": {},
            "inputs": [
                {
                    "description": "",
                    "name": "Megakaryocyte_rep2_reverse_read_%28SRR549358_2%29"
                }
            ],
            "label": "Megakaryocyte_rep2_reverse_read_%28SRR549358_2%29",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "left": 10,
                "top": 850
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "93902423-21b9-4060-ac8a-1b38e1dedac3",
            "workflow_outputs": []
        },
        "8": {
            "annotation": "",
            "content_id": null,
            "errors": null,
            "id": 8,
            "input_connections": {},
            "inputs": [
                {
                    "description": "",
                    "name": "RefSeq_reference_GTF_%28DSv2%29"
                }
            ],
            "label": "RefSeq_reference_GTF_%28DSv2%29",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "left": 10,
                "top": 970
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "401af9a6-2707-4345-9a8e-3f18c76ae29d",
            "workflow_outputs": []
        },
        "9": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 9,
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
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "2e24303c-68f7-4134-a16b-546d7387c2c8",
            "workflow_outputs": []
        },
        "10": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 10,
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
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "3b4288a8-ce41-4c5a-bd5d-ce6c39ba48c1",
            "workflow_outputs": []
        },
        "11": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "errors": null,
            "id": 11,
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
                "top": 970
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "tool_shed_repository": {
                "changeset_revision": "898b67846b47",
                "name": "trimmomatic",
                "owner": "pjbriggs",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"illuminaclip\": {\"do_illuminaclip\": \"false\", \"__current_case__\": 1}, \"operations\": [{\"__index__\": 0, \"operation\": {\"name\": \"SLIDINGWINDOW\", \"__current_case__\": 0, \"window_size\": \"4\", \"required_quality\": \"20\"}}], \"output_err\": \"false\", \"output_logs\": \"false\", \"readtype\": {\"single_or_paired\": \"pair_of_files\", \"__current_case__\": 1, \"fastq_r1_in\": null, \"fastq_r2_in\": null}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.38.0",
            "type": "tool",
            "uuid": "60f361ce-242a-4d76-a739-2be19d9ae488",
            "workflow_outputs": []
        },
        "12": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 12,
            "input_connections": {
                "input_file": {
                    "id": 2,
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
                "top": 250
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "66d92054-4b9e-47e7-9e60-a2b859820bd9",
            "workflow_outputs": []
        },
        "13": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 13,
            "input_connections": {
                "input_file": {
                    "id": 3,
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
                "top": 370
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "fc142148-902d-4191-a79d-c2bac4d5e840",
            "workflow_outputs": []
        },
        "14": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "errors": null,
            "id": 14,
            "input_connections": {
                "readtype|fastq_r1_in": {
                    "id": 2,
                    "output_name": "output"
                },
                "readtype|fastq_r2_in": {
                    "id": 3,
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
                "top": 1090
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "tool_shed_repository": {
                "changeset_revision": "898b67846b47",
                "name": "trimmomatic",
                "owner": "pjbriggs",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"illuminaclip\": {\"do_illuminaclip\": \"false\", \"__current_case__\": 1}, \"operations\": [{\"__index__\": 0, \"operation\": {\"name\": \"SLIDINGWINDOW\", \"__current_case__\": 0, \"window_size\": \"4\", \"required_quality\": \"20\"}}], \"output_err\": \"false\", \"output_logs\": \"false\", \"readtype\": {\"single_or_paired\": \"pair_of_files\", \"__current_case__\": 1, \"fastq_r1_in\": null, \"fastq_r2_in\": null}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.38.0",
            "type": "tool",
            "uuid": "6fd01f32-d2a0-4c32-89c8-ca16a999a5ac",
            "workflow_outputs": []
        },
        "15": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 15,
            "input_connections": {
                "input_file": {
                    "id": 4,
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
                "top": 490
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "89a28de7-681f-4728-b04c-9f646130ce96",
            "workflow_outputs": []
        },
        "16": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 16,
            "input_connections": {
                "input_file": {
                    "id": 5,
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
                "top": 610
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "83088aa4-2e4d-40d0-ab90-67a36b21d801",
            "workflow_outputs": []
        },
        "17": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "errors": null,
            "id": 17,
            "input_connections": {
                "readtype|fastq_r1_in": {
                    "id": 4,
                    "output_name": "output"
                },
                "readtype|fastq_r2_in": {
                    "id": 5,
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
                "top": 1210
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "tool_shed_repository": {
                "changeset_revision": "898b67846b47",
                "name": "trimmomatic",
                "owner": "pjbriggs",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"illuminaclip\": {\"do_illuminaclip\": \"false\", \"__current_case__\": 1}, \"operations\": [{\"__index__\": 0, \"operation\": {\"name\": \"SLIDINGWINDOW\", \"__current_case__\": 0, \"window_size\": \"4\", \"required_quality\": \"20\"}}], \"output_err\": \"false\", \"output_logs\": \"false\", \"readtype\": {\"single_or_paired\": \"pair_of_files\", \"__current_case__\": 1, \"fastq_r1_in\": null, \"fastq_r2_in\": null}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.38.0",
            "type": "tool",
            "uuid": "2470f424-3c4f-4b86-8919-57f487c57f99",
            "workflow_outputs": []
        },
        "18": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 18,
            "input_connections": {
                "input_file": {
                    "id": 6,
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
                "top": 730
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "04290bdd-8264-4385-a0c9-e522ccae1e63",
            "workflow_outputs": []
        },
        "19": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 19,
            "input_connections": {
                "input_file": {
                    "id": 7,
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
                "top": 850
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "72ea91c3-e214-417b-bfad-a902d85286c2",
            "workflow_outputs": []
        },
        "20": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "errors": null,
            "id": 20,
            "input_connections": {
                "readtype|fastq_r1_in": {
                    "id": 6,
                    "output_name": "output"
                },
                "readtype|fastq_r2_in": {
                    "id": 7,
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
                "top": 1330
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "tool_shed_repository": {
                "changeset_revision": "898b67846b47",
                "name": "trimmomatic",
                "owner": "pjbriggs",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"illuminaclip\": {\"do_illuminaclip\": \"false\", \"__current_case__\": 1}, \"operations\": [{\"__index__\": 0, \"operation\": {\"name\": \"SLIDINGWINDOW\", \"__current_case__\": 0, \"window_size\": \"4\", \"required_quality\": \"20\"}}], \"output_err\": \"false\", \"output_logs\": \"false\", \"readtype\": {\"single_or_paired\": \"pair_of_files\", \"__current_case__\": 1, \"fastq_r1_in\": null, \"fastq_r2_in\": null}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.38.0",
            "type": "tool",
            "uuid": "234c3fa0-91f7-41c4-b70c-11cc3b67c31e",
            "workflow_outputs": []
        },
        "21": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 21,
            "input_connections": {
                "input_file": {
                    "id": 11,
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
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "e0eda7e5-bd4c-4527-ac91-dc03e833981c",
            "workflow_outputs": []
        },
        "22": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 22,
            "input_connections": {
                "input_file": {
                    "id": 11,
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
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "bc03f84d-58be-4fb9-9431-66d62660f203",
            "workflow_outputs": []
        },
        "23": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/hisat2/hisat2/2.1.0+galaxy7",
            "errors": null,
            "id": 23,
            "input_connections": {
                "library|input_1": {
                    "id": 11,
                    "output_name": "fastq_out_r1_paired"
                },
                "library|input_2": {
                    "id": 11,
                    "output_name": "fastq_out_r2_paired"
                }
            },
            "inputs": [],
            "label": null,
            "name": "HISAT2",
            "outputs": [
                {
                    "name": "output_alignments",
                    "type": "bam"
                }
            ],
            "position": {
                "left": 450,
                "top": 970
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/hisat2/hisat2/2.1.0+galaxy7",
            "tool_shed_repository": {
                "changeset_revision": "26371a1df031",
                "name": "hisat2",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"adv\": {\"input_options\": {\"input_options_selector\": \"defaults\", \"__current_case__\": 0}, \"alignment_options\": {\"alignment_options_selector\": \"defaults\", \"__current_case__\": 0}, \"scoring_options\": {\"scoring_options_selector\": \"defaults\", \"__current_case__\": 0}, \"spliced_options\": {\"spliced_options_selector\": \"advanced\", \"__current_case__\": 1, \"canonical_penalty\": \"0\", \"noncanonical_penalty\": \"3\", \"function_type\": \"C\", \"constant_term\": \"0.0\", \"coefficient\": \"1.0\", \"nc_function_type\": \"C\", \"nc_constant_term\": \"-8.0\", \"nc_coefficient\": \"1.0\", \"min_intron\": \"20\", \"max_intron\": \"500000\", \"no_spliced_alignment_options\": {\"no_spliced_alignment\": \"\", \"__current_case__\": 1}, \"known_splice_gtf\": null, \"tma\": \"--dta\", \"notmplen\": \"false\", \"novel_splicesite_outfile\": \"false\"}, \"reporting_options\": {\"reporting_options_selector\": \"defaults\", \"__current_case__\": 0}, \"output_options\": {\"output_options_selector\": \"defaults\", \"__current_case__\": 0}, \"sam_options\": {\"sam_options_selector\": \"defaults\", \"__current_case__\": 0}, \"other_options\": {\"other_options_selector\": \"defaults\", \"__current_case__\": 0}}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"library\": {\"type\": \"paired\", \"__current_case__\": 1, \"input_1\": null, \"input_2\": null, \"rna_strandness\": \"FR\", \"paired_options\": {\"paired_options_selector\": \"defaults\", \"__current_case__\": 0}}, \"reference_genome\": {\"source\": \"indexed\", \"__current_case__\": 0, \"index\": \"mm10\"}, \"sum\": {\"new_summary\": \"false\", \"summary_file\": \"false\"}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.1.0+galaxy7",
            "type": "tool",
            "uuid": "94761f79-c5c5-4e67-9bbf-63242500478f",
            "workflow_outputs": []
        },
        "24": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 24,
            "input_connections": {
                "input_file": {
                    "id": 14,
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
                "top": 250
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "961272d2-5764-4285-bc99-c4adb902d4b8",
            "workflow_outputs": []
        },
        "25": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 25,
            "input_connections": {
                "input_file": {
                    "id": 14,
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
                "top": 370
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "9110ce59-07ed-4048-ae85-e1b3d1a595af",
            "workflow_outputs": []
        },
        "26": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/hisat2/hisat2/2.1.0+galaxy7",
            "errors": null,
            "id": 26,
            "input_connections": {
                "library|input_1": {
                    "id": 14,
                    "output_name": "fastq_out_r1_paired"
                },
                "library|input_2": {
                    "id": 14,
                    "output_name": "fastq_out_r2_paired"
                }
            },
            "inputs": [],
            "label": null,
            "name": "HISAT2",
            "outputs": [
                {
                    "name": "output_alignments",
                    "type": "bam"
                }
            ],
            "position": {
                "left": 450,
                "top": 1090
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/hisat2/hisat2/2.1.0+galaxy7",
            "tool_shed_repository": {
                "changeset_revision": "26371a1df031",
                "name": "hisat2",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"adv\": {\"input_options\": {\"input_options_selector\": \"defaults\", \"__current_case__\": 0}, \"alignment_options\": {\"alignment_options_selector\": \"defaults\", \"__current_case__\": 0}, \"scoring_options\": {\"scoring_options_selector\": \"defaults\", \"__current_case__\": 0}, \"spliced_options\": {\"spliced_options_selector\": \"advanced\", \"__current_case__\": 1, \"canonical_penalty\": \"0\", \"noncanonical_penalty\": \"3\", \"function_type\": \"C\", \"constant_term\": \"0.0\", \"coefficient\": \"1.0\", \"nc_function_type\": \"C\", \"nc_constant_term\": \"-8.0\", \"nc_coefficient\": \"1.0\", \"min_intron\": \"20\", \"max_intron\": \"500000\", \"no_spliced_alignment_options\": {\"no_spliced_alignment\": \"\", \"__current_case__\": 1}, \"known_splice_gtf\": null, \"tma\": \"--dta\", \"notmplen\": \"false\", \"novel_splicesite_outfile\": \"false\"}, \"reporting_options\": {\"reporting_options_selector\": \"defaults\", \"__current_case__\": 0}, \"output_options\": {\"output_options_selector\": \"defaults\", \"__current_case__\": 0}, \"sam_options\": {\"sam_options_selector\": \"defaults\", \"__current_case__\": 0}, \"other_options\": {\"other_options_selector\": \"defaults\", \"__current_case__\": 0}}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"library\": {\"type\": \"paired\", \"__current_case__\": 1, \"input_1\": null, \"input_2\": null, \"rna_strandness\": \"FR\", \"paired_options\": {\"paired_options_selector\": \"defaults\", \"__current_case__\": 0}}, \"reference_genome\": {\"source\": \"indexed\", \"__current_case__\": 0, \"index\": \"mm10\"}, \"sum\": {\"new_summary\": \"false\", \"summary_file\": \"false\"}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.1.0+galaxy7",
            "type": "tool",
            "uuid": "54bdd3af-df16-4565-9663-85ab8379520e",
            "workflow_outputs": []
        },
        "27": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 27,
            "input_connections": {
                "input_file": {
                    "id": 17,
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
                "top": 490
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "413f268f-8659-4d22-8670-e66935fd9ac6",
            "workflow_outputs": []
        },
        "28": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 28,
            "input_connections": {
                "input_file": {
                    "id": 17,
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
                "top": 610
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "176ffa71-498d-401b-a58a-9de914d7f240",
            "workflow_outputs": []
        },
        "29": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/hisat2/hisat2/2.1.0+galaxy7",
            "errors": null,
            "id": 29,
            "input_connections": {
                "library|input_1": {
                    "id": 17,
                    "output_name": "fastq_out_r1_paired"
                },
                "library|input_2": {
                    "id": 17,
                    "output_name": "fastq_out_r2_paired"
                }
            },
            "inputs": [],
            "label": null,
            "name": "HISAT2",
            "outputs": [
                {
                    "name": "output_alignments",
                    "type": "bam"
                }
            ],
            "position": {
                "left": 450,
                "top": 1210
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/hisat2/hisat2/2.1.0+galaxy7",
            "tool_shed_repository": {
                "changeset_revision": "26371a1df031",
                "name": "hisat2",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"adv\": {\"input_options\": {\"input_options_selector\": \"defaults\", \"__current_case__\": 0}, \"alignment_options\": {\"alignment_options_selector\": \"defaults\", \"__current_case__\": 0}, \"scoring_options\": {\"scoring_options_selector\": \"defaults\", \"__current_case__\": 0}, \"spliced_options\": {\"spliced_options_selector\": \"advanced\", \"__current_case__\": 1, \"canonical_penalty\": \"0\", \"noncanonical_penalty\": \"3\", \"function_type\": \"C\", \"constant_term\": \"0.0\", \"coefficient\": \"1.0\", \"nc_function_type\": \"C\", \"nc_constant_term\": \"-8.0\", \"nc_coefficient\": \"1.0\", \"min_intron\": \"20\", \"max_intron\": \"500000\", \"no_spliced_alignment_options\": {\"no_spliced_alignment\": \"\", \"__current_case__\": 1}, \"known_splice_gtf\": null, \"tma\": \"--dta\", \"notmplen\": \"false\", \"novel_splicesite_outfile\": \"false\"}, \"reporting_options\": {\"reporting_options_selector\": \"defaults\", \"__current_case__\": 0}, \"output_options\": {\"output_options_selector\": \"defaults\", \"__current_case__\": 0}, \"sam_options\": {\"sam_options_selector\": \"defaults\", \"__current_case__\": 0}, \"other_options\": {\"other_options_selector\": \"defaults\", \"__current_case__\": 0}}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"library\": {\"type\": \"paired\", \"__current_case__\": 1, \"input_1\": null, \"input_2\": null, \"rna_strandness\": \"FR\", \"paired_options\": {\"paired_options_selector\": \"defaults\", \"__current_case__\": 0}}, \"reference_genome\": {\"source\": \"indexed\", \"__current_case__\": 0, \"index\": \"mm10\"}, \"sum\": {\"new_summary\": \"false\", \"summary_file\": \"false\"}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.1.0+galaxy7",
            "type": "tool",
            "uuid": "99a75b01-a173-4001-bf35-f7175e485d1c",
            "workflow_outputs": []
        },
        "30": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 30,
            "input_connections": {
                "input_file": {
                    "id": 20,
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
                "top": 730
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "f9622d95-d383-437c-bf58-46a2a610409b",
            "workflow_outputs": []
        },
        "31": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 31,
            "input_connections": {
                "input_file": {
                    "id": 20,
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
                "top": 850
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"contaminants\": null, \"input_file\": null, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "35410e95-5753-4ac9-88a5-e14da119f61e",
            "workflow_outputs": []
        },
        "32": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/hisat2/hisat2/2.1.0+galaxy7",
            "errors": null,
            "id": 32,
            "input_connections": {
                "library|input_1": {
                    "id": 20,
                    "output_name": "fastq_out_r1_paired"
                },
                "library|input_2": {
                    "id": 20,
                    "output_name": "fastq_out_r2_paired"
                }
            },
            "inputs": [],
            "label": null,
            "name": "HISAT2",
            "outputs": [
                {
                    "name": "output_alignments",
                    "type": "bam"
                }
            ],
            "position": {
                "left": 450,
                "top": 1330
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/hisat2/hisat2/2.1.0+galaxy7",
            "tool_shed_repository": {
                "changeset_revision": "26371a1df031",
                "name": "hisat2",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"adv\": {\"input_options\": {\"input_options_selector\": \"defaults\", \"__current_case__\": 0}, \"alignment_options\": {\"alignment_options_selector\": \"defaults\", \"__current_case__\": 0}, \"scoring_options\": {\"scoring_options_selector\": \"defaults\", \"__current_case__\": 0}, \"spliced_options\": {\"spliced_options_selector\": \"advanced\", \"__current_case__\": 1, \"canonical_penalty\": \"0\", \"noncanonical_penalty\": \"3\", \"function_type\": \"C\", \"constant_term\": \"0.0\", \"coefficient\": \"1.0\", \"nc_function_type\": \"C\", \"nc_constant_term\": \"-8.0\", \"nc_coefficient\": \"1.0\", \"min_intron\": \"20\", \"max_intron\": \"500000\", \"no_spliced_alignment_options\": {\"no_spliced_alignment\": \"\", \"__current_case__\": 1}, \"known_splice_gtf\": null, \"tma\": \"--dta\", \"notmplen\": \"false\", \"novel_splicesite_outfile\": \"false\"}, \"reporting_options\": {\"reporting_options_selector\": \"defaults\", \"__current_case__\": 0}, \"output_options\": {\"output_options_selector\": \"defaults\", \"__current_case__\": 0}, \"sam_options\": {\"sam_options_selector\": \"defaults\", \"__current_case__\": 0}, \"other_options\": {\"other_options_selector\": \"defaults\", \"__current_case__\": 0}}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"library\": {\"type\": \"paired\", \"__current_case__\": 1, \"input_1\": null, \"input_2\": null, \"rna_strandness\": \"FR\", \"paired_options\": {\"paired_options_selector\": \"defaults\", \"__current_case__\": 0}}, \"reference_genome\": {\"source\": \"indexed\", \"__current_case__\": 0, \"index\": \"mm10\"}, \"sum\": {\"new_summary\": \"false\", \"summary_file\": \"false\"}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.1.0+galaxy7",
            "type": "tool",
            "uuid": "e3767419-daac-42a5-8873-b2c932197da4",
            "workflow_outputs": []
        },
        "33": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/stringtie/stringtie/2.1.1",
            "errors": null,
            "id": 33,
            "input_connections": {
                "input_bam": {
                    "id": 23,
                    "output_name": "output_alignments"
                }
            },
            "inputs": [],
            "label": null,
            "name": "StringTie",
            "outputs": [
                {
                    "name": "output_gtf",
                    "type": "gtf"
                }
            ],
            "position": {
                "left": 670,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/stringtie/stringtie/2.1.1",
            "tool_shed_repository": {
                "changeset_revision": "1ebd14235b92",
                "name": "stringtie",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"adv\": {\"abundance_estimation\": \"false\", \"omit_sequences\": \"\", \"name_prefix\": \"\", \"fraction\": \"0.15\", \"min_tlen\": \"200\", \"min_anchor_len\": \"10\", \"min_anchor_cov\": \"1\", \"min_bundle_cov\": \"2\", \"bdist\": \"50\", \"bundle_fraction\": \"0.95\", \"disable_trimming\": \"false\", \"multi_mapping\": \"false\"}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"guide\": {\"use_guide\": \"no\", \"__current_case__\": 0}, \"input_bam\": null, \"long_reads\": \"false\", \"rna_strandness\": \"--fr\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.1.1",
            "type": "tool",
            "uuid": "f0b823fb-8187-441c-899b-525361d83176",
            "workflow_outputs": []
        },
        "34": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "errors": null,
            "id": 34,
            "input_connections": {
                "bamInput": {
                    "id": 23,
                    "output_name": "output_alignments"
                }
            },
            "inputs": [],
            "label": null,
            "name": "bamCoverage",
            "outputs": [
                {
                    "name": "outFileName",
                    "type": "bigwig"
                }
            ],
            "position": {
                "left": 670,
                "top": 490
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "tool_shed_repository": {
                "changeset_revision": "bb1e4f63e0e6",
                "name": "deeptools_bam_coverage",
                "owner": "bgruening",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"advancedOpt\": {\"showAdvancedOpt\": \"yes\", \"__current_case__\": 1, \"scaleFactor\": \"1.0\", \"smoothLength\": null, \"ignoreForNormalization\": \"\", \"skipNAs\": \"false\", \"doExtendCustom\": {\"doExtend\": \"no\", \"__current_case__\": 0}, \"ignoreDuplicates\": \"false\", \"centerReads\": \"false\", \"minMappingQuality\": \"1\", \"samFlagInclude\": null, \"samFlagExclude\": null, \"minFragmentLength\": \"0\", \"maxFragmentLength\": \"0\", \"MNase\": \"false\", \"Offset\": \"\", \"filterRNAstrand\": \"forward\", \"blackListFileName\": null}, \"bamInput\": null, \"binSize\": \"1\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"exactScaling\": \"false\", \"outFileFormat\": \"bigwig\", \"region\": \"\", \"scaling\": {\"type\": \"1x\", \"__current_case__\": 4, \"effectiveGenomeSize\": {\"effectiveGenomeSize_opt\": \"2308125349\", \"__current_case__\": 7}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "3.3.2.0.0",
            "type": "tool",
            "uuid": "d8051a5c-91b2-40dc-88bf-ce108b8bbcaa",
            "workflow_outputs": []
        },
        "35": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "errors": null,
            "id": 35,
            "input_connections": {
                "bamInput": {
                    "id": 23,
                    "output_name": "output_alignments"
                }
            },
            "inputs": [],
            "label": null,
            "name": "bamCoverage",
            "outputs": [
                {
                    "name": "outFileName",
                    "type": "bigwig"
                }
            ],
            "position": {
                "left": 670,
                "top": 970
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "tool_shed_repository": {
                "changeset_revision": "bb1e4f63e0e6",
                "name": "deeptools_bam_coverage",
                "owner": "bgruening",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"advancedOpt\": {\"showAdvancedOpt\": \"yes\", \"__current_case__\": 1, \"scaleFactor\": \"1.0\", \"smoothLength\": null, \"ignoreForNormalization\": \"\", \"skipNAs\": \"false\", \"doExtendCustom\": {\"doExtend\": \"no\", \"__current_case__\": 0}, \"ignoreDuplicates\": \"false\", \"centerReads\": \"false\", \"minMappingQuality\": \"1\", \"samFlagInclude\": null, \"samFlagExclude\": null, \"minFragmentLength\": \"0\", \"maxFragmentLength\": \"0\", \"MNase\": \"false\", \"Offset\": \"\", \"filterRNAstrand\": \"reverse\", \"blackListFileName\": null}, \"bamInput\": null, \"binSize\": \"1\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"exactScaling\": \"false\", \"outFileFormat\": \"bigwig\", \"region\": \"\", \"scaling\": {\"type\": \"1x\", \"__current_case__\": 4, \"effectiveGenomeSize\": {\"effectiveGenomeSize_opt\": \"2308125349\", \"__current_case__\": 7}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "3.3.2.0.0",
            "type": "tool",
            "uuid": "0cd62225-b801-4bee-9c46-788ecad4847e",
            "workflow_outputs": []
        },
        "36": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/stringtie/stringtie/2.1.1",
            "errors": null,
            "id": 36,
            "input_connections": {
                "input_bam": {
                    "id": 26,
                    "output_name": "output_alignments"
                }
            },
            "inputs": [],
            "label": null,
            "name": "StringTie",
            "outputs": [
                {
                    "name": "output_gtf",
                    "type": "gtf"
                }
            ],
            "position": {
                "left": 670,
                "top": 130
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/stringtie/stringtie/2.1.1",
            "tool_shed_repository": {
                "changeset_revision": "1ebd14235b92",
                "name": "stringtie",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"adv\": {\"abundance_estimation\": \"false\", \"omit_sequences\": \"\", \"name_prefix\": \"\", \"fraction\": \"0.15\", \"min_tlen\": \"200\", \"min_anchor_len\": \"10\", \"min_anchor_cov\": \"1\", \"min_bundle_cov\": \"2\", \"bdist\": \"50\", \"bundle_fraction\": \"0.95\", \"disable_trimming\": \"false\", \"multi_mapping\": \"false\"}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"guide\": {\"use_guide\": \"no\", \"__current_case__\": 0}, \"input_bam\": null, \"long_reads\": \"false\", \"rna_strandness\": \"--fr\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.1.1",
            "type": "tool",
            "uuid": "cf9bd6eb-c389-4620-a4e5-d838eacc9594",
            "workflow_outputs": []
        },
        "37": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "errors": null,
            "id": 37,
            "input_connections": {
                "bamInput": {
                    "id": 26,
                    "output_name": "output_alignments"
                }
            },
            "inputs": [],
            "label": null,
            "name": "bamCoverage",
            "outputs": [
                {
                    "name": "outFileName",
                    "type": "bigwig"
                }
            ],
            "position": {
                "left": 670,
                "top": 610
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "tool_shed_repository": {
                "changeset_revision": "bb1e4f63e0e6",
                "name": "deeptools_bam_coverage",
                "owner": "bgruening",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"advancedOpt\": {\"showAdvancedOpt\": \"yes\", \"__current_case__\": 1, \"scaleFactor\": \"1.0\", \"smoothLength\": null, \"ignoreForNormalization\": \"\", \"skipNAs\": \"false\", \"doExtendCustom\": {\"doExtend\": \"no\", \"__current_case__\": 0}, \"ignoreDuplicates\": \"false\", \"centerReads\": \"false\", \"minMappingQuality\": \"1\", \"samFlagInclude\": null, \"samFlagExclude\": null, \"minFragmentLength\": \"0\", \"maxFragmentLength\": \"0\", \"MNase\": \"false\", \"Offset\": \"\", \"filterRNAstrand\": \"forward\", \"blackListFileName\": null}, \"bamInput\": null, \"binSize\": \"1\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"exactScaling\": \"false\", \"outFileFormat\": \"bigwig\", \"region\": \"\", \"scaling\": {\"type\": \"1x\", \"__current_case__\": 4, \"effectiveGenomeSize\": {\"effectiveGenomeSize_opt\": \"2308125349\", \"__current_case__\": 7}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "3.3.2.0.0",
            "type": "tool",
            "uuid": "9edbd6ea-45c3-4da3-b4b7-9b3373af2a7d",
            "workflow_outputs": []
        },
        "38": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "errors": null,
            "id": 38,
            "input_connections": {
                "bamInput": {
                    "id": 26,
                    "output_name": "output_alignments"
                }
            },
            "inputs": [],
            "label": null,
            "name": "bamCoverage",
            "outputs": [
                {
                    "name": "outFileName",
                    "type": "bigwig"
                }
            ],
            "position": {
                "left": 670,
                "top": 1090
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "tool_shed_repository": {
                "changeset_revision": "bb1e4f63e0e6",
                "name": "deeptools_bam_coverage",
                "owner": "bgruening",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"advancedOpt\": {\"showAdvancedOpt\": \"yes\", \"__current_case__\": 1, \"scaleFactor\": \"1.0\", \"smoothLength\": null, \"ignoreForNormalization\": \"\", \"skipNAs\": \"false\", \"doExtendCustom\": {\"doExtend\": \"no\", \"__current_case__\": 0}, \"ignoreDuplicates\": \"false\", \"centerReads\": \"false\", \"minMappingQuality\": \"1\", \"samFlagInclude\": null, \"samFlagExclude\": null, \"minFragmentLength\": \"0\", \"maxFragmentLength\": \"0\", \"MNase\": \"false\", \"Offset\": \"\", \"filterRNAstrand\": \"reverse\", \"blackListFileName\": null}, \"bamInput\": null, \"binSize\": \"1\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"exactScaling\": \"false\", \"outFileFormat\": \"bigwig\", \"region\": \"\", \"scaling\": {\"type\": \"1x\", \"__current_case__\": 4, \"effectiveGenomeSize\": {\"effectiveGenomeSize_opt\": \"2308125349\", \"__current_case__\": 7}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "3.3.2.0.0",
            "type": "tool",
            "uuid": "14d9e0d4-6496-427a-933b-3ef9205ae3bd",
            "workflow_outputs": []
        },
        "39": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/stringtie/stringtie/2.1.1",
            "errors": null,
            "id": 39,
            "input_connections": {
                "input_bam": {
                    "id": 29,
                    "output_name": "output_alignments"
                }
            },
            "inputs": [],
            "label": null,
            "name": "StringTie",
            "outputs": [
                {
                    "name": "output_gtf",
                    "type": "gtf"
                }
            ],
            "position": {
                "left": 670,
                "top": 250
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/stringtie/stringtie/2.1.1",
            "tool_shed_repository": {
                "changeset_revision": "1ebd14235b92",
                "name": "stringtie",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"adv\": {\"abundance_estimation\": \"false\", \"omit_sequences\": \"\", \"name_prefix\": \"\", \"fraction\": \"0.15\", \"min_tlen\": \"200\", \"min_anchor_len\": \"10\", \"min_anchor_cov\": \"1\", \"min_bundle_cov\": \"2\", \"bdist\": \"50\", \"bundle_fraction\": \"0.95\", \"disable_trimming\": \"false\", \"multi_mapping\": \"false\"}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"guide\": {\"use_guide\": \"no\", \"__current_case__\": 0}, \"input_bam\": null, \"long_reads\": \"false\", \"rna_strandness\": \"--fr\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.1.1",
            "type": "tool",
            "uuid": "f491479b-f1a8-46d7-ad32-b45ef323a218",
            "workflow_outputs": []
        },
        "40": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "errors": null,
            "id": 40,
            "input_connections": {
                "bamInput": {
                    "id": 29,
                    "output_name": "output_alignments"
                }
            },
            "inputs": [],
            "label": null,
            "name": "bamCoverage",
            "outputs": [
                {
                    "name": "outFileName",
                    "type": "bigwig"
                }
            ],
            "position": {
                "left": 670,
                "top": 730
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "tool_shed_repository": {
                "changeset_revision": "bb1e4f63e0e6",
                "name": "deeptools_bam_coverage",
                "owner": "bgruening",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"advancedOpt\": {\"showAdvancedOpt\": \"yes\", \"__current_case__\": 1, \"scaleFactor\": \"1.0\", \"smoothLength\": null, \"ignoreForNormalization\": \"\", \"skipNAs\": \"false\", \"doExtendCustom\": {\"doExtend\": \"no\", \"__current_case__\": 0}, \"ignoreDuplicates\": \"false\", \"centerReads\": \"false\", \"minMappingQuality\": \"1\", \"samFlagInclude\": null, \"samFlagExclude\": null, \"minFragmentLength\": \"0\", \"maxFragmentLength\": \"0\", \"MNase\": \"false\", \"Offset\": \"\", \"filterRNAstrand\": \"forward\", \"blackListFileName\": null}, \"bamInput\": null, \"binSize\": \"1\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"exactScaling\": \"false\", \"outFileFormat\": \"bigwig\", \"region\": \"\", \"scaling\": {\"type\": \"1x\", \"__current_case__\": 4, \"effectiveGenomeSize\": {\"effectiveGenomeSize_opt\": \"2308125349\", \"__current_case__\": 7}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "3.3.2.0.0",
            "type": "tool",
            "uuid": "96b464fb-4825-4e03-a98e-89dc3b1f52e2",
            "workflow_outputs": []
        },
        "41": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "errors": null,
            "id": 41,
            "input_connections": {
                "bamInput": {
                    "id": 29,
                    "output_name": "output_alignments"
                }
            },
            "inputs": [],
            "label": null,
            "name": "bamCoverage",
            "outputs": [
                {
                    "name": "outFileName",
                    "type": "bigwig"
                }
            ],
            "position": {
                "left": 670,
                "top": 1210
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "tool_shed_repository": {
                "changeset_revision": "bb1e4f63e0e6",
                "name": "deeptools_bam_coverage",
                "owner": "bgruening",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"advancedOpt\": {\"showAdvancedOpt\": \"yes\", \"__current_case__\": 1, \"scaleFactor\": \"1.0\", \"smoothLength\": null, \"ignoreForNormalization\": \"\", \"skipNAs\": \"false\", \"doExtendCustom\": {\"doExtend\": \"no\", \"__current_case__\": 0}, \"ignoreDuplicates\": \"false\", \"centerReads\": \"false\", \"minMappingQuality\": \"1\", \"samFlagInclude\": null, \"samFlagExclude\": null, \"minFragmentLength\": \"0\", \"maxFragmentLength\": \"0\", \"MNase\": \"false\", \"Offset\": \"\", \"filterRNAstrand\": \"reverse\", \"blackListFileName\": null}, \"bamInput\": null, \"binSize\": \"1\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"exactScaling\": \"false\", \"outFileFormat\": \"bigwig\", \"region\": \"\", \"scaling\": {\"type\": \"1x\", \"__current_case__\": 4, \"effectiveGenomeSize\": {\"effectiveGenomeSize_opt\": \"2308125349\", \"__current_case__\": 7}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "3.3.2.0.0",
            "type": "tool",
            "uuid": "c5e3d739-d77d-4e4b-9c69-e006a02849a0",
            "workflow_outputs": []
        },
        "42": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/stringtie/stringtie/2.1.1",
            "errors": null,
            "id": 42,
            "input_connections": {
                "input_bam": {
                    "id": 32,
                    "output_name": "output_alignments"
                }
            },
            "inputs": [],
            "label": null,
            "name": "StringTie",
            "outputs": [
                {
                    "name": "output_gtf",
                    "type": "gtf"
                }
            ],
            "position": {
                "left": 670,
                "top": 370
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/stringtie/stringtie/2.1.1",
            "tool_shed_repository": {
                "changeset_revision": "1ebd14235b92",
                "name": "stringtie",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"adv\": {\"abundance_estimation\": \"false\", \"omit_sequences\": \"\", \"name_prefix\": \"\", \"fraction\": \"0.15\", \"min_tlen\": \"200\", \"min_anchor_len\": \"10\", \"min_anchor_cov\": \"1\", \"min_bundle_cov\": \"2\", \"bdist\": \"50\", \"bundle_fraction\": \"0.95\", \"disable_trimming\": \"false\", \"multi_mapping\": \"false\"}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"guide\": {\"use_guide\": \"no\", \"__current_case__\": 0}, \"input_bam\": null, \"long_reads\": \"false\", \"rna_strandness\": \"--fr\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.1.1",
            "type": "tool",
            "uuid": "e7476c8d-f184-4496-a0ca-70cf5b20dfbb",
            "workflow_outputs": []
        },
        "43": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "errors": null,
            "id": 43,
            "input_connections": {
                "bamInput": {
                    "id": 32,
                    "output_name": "output_alignments"
                }
            },
            "inputs": [],
            "label": null,
            "name": "bamCoverage",
            "outputs": [
                {
                    "name": "outFileName",
                    "type": "bigwig"
                }
            ],
            "position": {
                "left": 670,
                "top": 850
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "tool_shed_repository": {
                "changeset_revision": "bb1e4f63e0e6",
                "name": "deeptools_bam_coverage",
                "owner": "bgruening",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"advancedOpt\": {\"showAdvancedOpt\": \"yes\", \"__current_case__\": 1, \"scaleFactor\": \"1.0\", \"smoothLength\": null, \"ignoreForNormalization\": \"\", \"skipNAs\": \"false\", \"doExtendCustom\": {\"doExtend\": \"no\", \"__current_case__\": 0}, \"ignoreDuplicates\": \"false\", \"centerReads\": \"false\", \"minMappingQuality\": \"1\", \"samFlagInclude\": null, \"samFlagExclude\": null, \"minFragmentLength\": \"0\", \"maxFragmentLength\": \"0\", \"MNase\": \"false\", \"Offset\": \"\", \"filterRNAstrand\": \"forward\", \"blackListFileName\": null}, \"bamInput\": null, \"binSize\": \"1\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"exactScaling\": \"false\", \"outFileFormat\": \"bigwig\", \"region\": \"\", \"scaling\": {\"type\": \"1x\", \"__current_case__\": 4, \"effectiveGenomeSize\": {\"effectiveGenomeSize_opt\": \"2308125349\", \"__current_case__\": 7}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "3.3.2.0.0",
            "type": "tool",
            "uuid": "dfe44cd2-fb76-46eb-8ac0-fee4c04f9d37",
            "workflow_outputs": []
        },
        "44": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "errors": null,
            "id": 44,
            "input_connections": {
                "bamInput": {
                    "id": 32,
                    "output_name": "output_alignments"
                }
            },
            "inputs": [],
            "label": null,
            "name": "bamCoverage",
            "outputs": [
                {
                    "name": "outFileName",
                    "type": "bigwig"
                }
            ],
            "position": {
                "left": 670,
                "top": 1330
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/bgruening/deeptools_bam_coverage/deeptools_bam_coverage/3.3.2.0.0",
            "tool_shed_repository": {
                "changeset_revision": "bb1e4f63e0e6",
                "name": "deeptools_bam_coverage",
                "owner": "bgruening",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bam\", \"advancedOpt\": {\"showAdvancedOpt\": \"yes\", \"__current_case__\": 1, \"scaleFactor\": \"1.0\", \"smoothLength\": null, \"ignoreForNormalization\": \"\", \"skipNAs\": \"false\", \"doExtendCustom\": {\"doExtend\": \"no\", \"__current_case__\": 0}, \"ignoreDuplicates\": \"false\", \"centerReads\": \"false\", \"minMappingQuality\": \"1\", \"samFlagInclude\": null, \"samFlagExclude\": null, \"minFragmentLength\": \"0\", \"maxFragmentLength\": \"0\", \"MNase\": \"false\", \"Offset\": \"\", \"filterRNAstrand\": \"reverse\", \"blackListFileName\": null}, \"bamInput\": null, \"binSize\": \"1\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"exactScaling\": \"false\", \"outFileFormat\": \"bigwig\", \"region\": \"\", \"scaling\": {\"type\": \"1x\", \"__current_case__\": 4, \"effectiveGenomeSize\": {\"effectiveGenomeSize_opt\": \"2308125349\", \"__current_case__\": 7}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "3.3.2.0.0",
            "type": "tool",
            "uuid": "64f9c277-aca7-4850-b7b0-fe15a6914637",
            "workflow_outputs": []
        },
        "45": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/stringtie/stringtie_merge/2.1.1",
            "errors": null,
            "id": 45,
            "input_connections": {
                "guide_gff": {
                    "id": 8,
                    "output_name": "output"
                },
                "input_gtf": [
                    {
                        "id": 33,
                        "output_name": "output_gtf"
                    },
                    {
                        "id": 36,
                        "output_name": "output_gtf"
                    },
                    {
                        "id": 39,
                        "output_name": "output_gtf"
                    },
                    {
                        "id": 42,
                        "output_name": "output_gtf"
                    }
                ]
            },
            "inputs": [],
            "label": null,
            "name": "StringTie merge",
            "outputs": [
                {
                    "name": "out_gtf",
                    "type": "gtf"
                }
            ],
            "position": {
                "left": 890,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/stringtie/stringtie_merge/2.1.1",
            "tool_shed_repository": {
                "changeset_revision": "1ebd14235b92",
                "name": "stringtie",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"gtf\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"gap_len\": \"250\", \"guide_gff\": null, \"input_gtf\": null, \"keep_introns\": \"false\", \"min_cov\": \"0\", \"min_fpkm\": \"1.0\", \"min_iso\": \"0.01\", \"min_len\": \"50\", \"min_tpm\": \"1.0\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.1.1",
            "type": "tool",
            "uuid": "20769b95-f0fb-41c9-8618-1fb0ded4935a",
            "workflow_outputs": []
        },
        "46": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/gffcompare/gffcompare/0.11.2",
            "errors": null,
            "id": 46,
            "input_connections": {
                "annotation|ref_source|reference_annotation": {
                    "id": 8,
                    "output_name": "output"
                },
                "gffinputs": {
                    "id": 45,
                    "output_name": "out_gtf"
                }
            },
            "inputs": [],
            "label": null,
            "name": "GffCompare",
            "outputs": [
                {
                    "name": "refmap_output",
                    "type": "input"
                },
                {
                    "name": "tmap_output",
                    "type": "input"
                },
                {
                    "name": "transcripts_stats",
                    "type": "txt"
                },
                {
                    "name": "transcripts_loci",
                    "type": "tabular"
                },
                {
                    "name": "transcripts_tracking",
                    "type": "tabular"
                },
                {
                    "name": "transcripts_annotated",
                    "type": "gtf"
                }
            ],
            "position": {
                "left": 1110,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/gffcompare/gffcompare/0.11.2",
            "tool_shed_repository": {
                "changeset_revision": "0f710191a66d",
                "name": "gffcompare",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"gtf\", \"adv_output\": {\"p\": \"TCONS\", \"C\": \"false\", \"A\": \"false\", \"X\": \"false\", \"K\": \"false\"}, \"annotation\": {\"use_ref_annotation\": \"Yes\", \"__current_case__\": 0, \"ref_source\": {\"ref_source_sel\": \"history\", \"__current_case__\": 1, \"reference_annotation\": null}, \"ignore_nonoverlapping_reference\": \"false\", \"ignore_nonoverlapping_transfrags\": \"false\", \"strict_match\": \"false\", \"refmap_tmap\": [\"refmap\", \"tmap\"]}, \"chr_stats\": \"false\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"discard_duplicates\": \"\", \"discard_single_exon\": \"\", \"gffinputs\": null, \"max_dist_exon\": \"100\", \"max_dist_group\": \"100\", \"no_merge\": \"false\", \"seq_data\": {\"use_seq_data\": \"Yes\", \"__current_case__\": 1, \"seq_source\": {\"index_source\": \"cached\", \"__current_case__\": 0, \"index\": \"mm10\"}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.11.2",
            "type": "tool",
            "uuid": "661aa195-b872-459d-a8b3-56fc2075b130",
            "workflow_outputs": []
        },
        "47": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/featurecounts/featurecounts/2.0.1",
            "errors": null,
            "id": 47,
            "input_connections": {
                "alignment": {
                    "id": 23,
                    "output_name": "output_alignments"
                },
                "anno|reference_gene_sets": {
                    "id": 46,
                    "output_name": "transcripts_annotated"
                }
            },
            "inputs": [],
            "label": null,
            "name": "featureCounts",
            "outputs": [
                {
                    "name": "output_short",
                    "type": "tabular"
                },
                {
                    "name": "output_summary",
                    "type": "tabular"
                }
            ],
            "position": {
                "left": 1330,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/featurecounts/featurecounts/2.0.1",
            "tool_shed_repository": {
                "changeset_revision": "ea04b737afa0",
                "name": "featurecounts",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"alignment\": null, \"anno\": {\"anno_select\": \"history\", \"__current_case__\": 2, \"reference_gene_sets\": null}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"extended_parameters\": {\"gff_feature_type\": \"exon\", \"gff_feature_attribute\": \"transcript_id\", \"summarization_level\": \"false\", \"multifeatures\": {\"multifeat\": \"\", \"__current_case__\": 0}, \"mapping_quality\": \"0\", \"exon_exon_junction_read_counting_enabled\": {\"count_exon_exon_junction_reads\": \"false\", \"__current_case__\": 1}, \"long_reads\": \"false\", \"by_read_group\": \"false\", \"largest_overlap\": \"false\", \"min_overlap\": \"1\", \"frac_overlap\": \"0\", \"frac_overlap_feature\": \"0\", \"read_extension_5p\": \"0\", \"read_extension_3p\": \"0\", \"read_reduction\": \"\", \"primary\": \"false\", \"ignore_dup\": \"false\", \"R\": \"false\", \"count_split_alignments_only\": \"false\"}, \"format\": \"tabdel_short\", \"include_feature_length_file\": \"false\", \"pe_parameters\": {\"fragment_counting_enabled\": {\"fragment_counting\": \" -p\", \"__current_case__\": 0, \"check_distance_enabled\": {\"check_distance\": \"false\", \"__current_case__\": 1}}, \"only_both_ends\": \"false\", \"exclude_chimerics\": \"true\"}, \"strand_specificity\": \"1\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.0.1",
            "type": "tool",
            "uuid": "e6a17a70-f663-4608-b6bd-63cc500011a8",
            "workflow_outputs": []
        },
        "48": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/featurecounts/featurecounts/2.0.1",
            "errors": null,
            "id": 48,
            "input_connections": {
                "alignment": {
                    "id": 26,
                    "output_name": "output_alignments"
                },
                "anno|reference_gene_sets": {
                    "id": 46,
                    "output_name": "transcripts_annotated"
                }
            },
            "inputs": [],
            "label": null,
            "name": "featureCounts",
            "outputs": [
                {
                    "name": "output_short",
                    "type": "tabular"
                },
                {
                    "name": "output_summary",
                    "type": "tabular"
                }
            ],
            "position": {
                "left": 1330,
                "top": 130
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/featurecounts/featurecounts/2.0.1",
            "tool_shed_repository": {
                "changeset_revision": "ea04b737afa0",
                "name": "featurecounts",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"alignment\": null, \"anno\": {\"anno_select\": \"history\", \"__current_case__\": 2, \"reference_gene_sets\": null}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"extended_parameters\": {\"gff_feature_type\": \"exon\", \"gff_feature_attribute\": \"transcript_id\", \"summarization_level\": \"false\", \"multifeatures\": {\"multifeat\": \"\", \"__current_case__\": 0}, \"mapping_quality\": \"0\", \"exon_exon_junction_read_counting_enabled\": {\"count_exon_exon_junction_reads\": \"false\", \"__current_case__\": 1}, \"long_reads\": \"false\", \"by_read_group\": \"false\", \"largest_overlap\": \"false\", \"min_overlap\": \"1\", \"frac_overlap\": \"0\", \"frac_overlap_feature\": \"0\", \"read_extension_5p\": \"0\", \"read_extension_3p\": \"0\", \"read_reduction\": \"\", \"primary\": \"false\", \"ignore_dup\": \"false\", \"R\": \"false\", \"count_split_alignments_only\": \"false\"}, \"format\": \"tabdel_short\", \"include_feature_length_file\": \"false\", \"pe_parameters\": {\"fragment_counting_enabled\": {\"fragment_counting\": \" -p\", \"__current_case__\": 0, \"check_distance_enabled\": {\"check_distance\": \"false\", \"__current_case__\": 1}}, \"only_both_ends\": \"false\", \"exclude_chimerics\": \"true\"}, \"strand_specificity\": \"1\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.0.1",
            "type": "tool",
            "uuid": "5f716d61-2f96-4515-ba55-b89c7a60baa4",
            "workflow_outputs": []
        },
        "49": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/featurecounts/featurecounts/2.0.1",
            "errors": null,
            "id": 49,
            "input_connections": {
                "alignment": {
                    "id": 29,
                    "output_name": "output_alignments"
                },
                "anno|reference_gene_sets": {
                    "id": 46,
                    "output_name": "transcripts_annotated"
                }
            },
            "inputs": [],
            "label": null,
            "name": "featureCounts",
            "outputs": [
                {
                    "name": "output_short",
                    "type": "tabular"
                },
                {
                    "name": "output_summary",
                    "type": "tabular"
                }
            ],
            "position": {
                "left": 1330,
                "top": 250
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/featurecounts/featurecounts/2.0.1",
            "tool_shed_repository": {
                "changeset_revision": "ea04b737afa0",
                "name": "featurecounts",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"alignment\": null, \"anno\": {\"anno_select\": \"history\", \"__current_case__\": 2, \"reference_gene_sets\": null}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"extended_parameters\": {\"gff_feature_type\": \"exon\", \"gff_feature_attribute\": \"transcript_id\", \"summarization_level\": \"false\", \"multifeatures\": {\"multifeat\": \"\", \"__current_case__\": 0}, \"mapping_quality\": \"0\", \"exon_exon_junction_read_counting_enabled\": {\"count_exon_exon_junction_reads\": \"false\", \"__current_case__\": 1}, \"long_reads\": \"false\", \"by_read_group\": \"false\", \"largest_overlap\": \"false\", \"min_overlap\": \"1\", \"frac_overlap\": \"0\", \"frac_overlap_feature\": \"0\", \"read_extension_5p\": \"0\", \"read_extension_3p\": \"0\", \"read_reduction\": \"\", \"primary\": \"false\", \"ignore_dup\": \"false\", \"R\": \"false\", \"count_split_alignments_only\": \"false\"}, \"format\": \"tabdel_short\", \"include_feature_length_file\": \"false\", \"pe_parameters\": {\"fragment_counting_enabled\": {\"fragment_counting\": \" -p\", \"__current_case__\": 0, \"check_distance_enabled\": {\"check_distance\": \"false\", \"__current_case__\": 1}}, \"only_both_ends\": \"false\", \"exclude_chimerics\": \"true\"}, \"strand_specificity\": \"1\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.0.1",
            "type": "tool",
            "uuid": "39119d99-d462-48e2-87eb-d9bda62f69f1",
            "workflow_outputs": []
        },
        "50": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/featurecounts/featurecounts/2.0.1",
            "errors": null,
            "id": 50,
            "input_connections": {
                "alignment": {
                    "id": 32,
                    "output_name": "output_alignments"
                },
                "anno|reference_gene_sets": {
                    "id": 46,
                    "output_name": "transcripts_annotated"
                }
            },
            "inputs": [],
            "label": null,
            "name": "featureCounts",
            "outputs": [
                {
                    "name": "output_short",
                    "type": "tabular"
                },
                {
                    "name": "output_summary",
                    "type": "tabular"
                }
            ],
            "position": {
                "left": 1330,
                "top": 370
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/featurecounts/featurecounts/2.0.1",
            "tool_shed_repository": {
                "changeset_revision": "ea04b737afa0",
                "name": "featurecounts",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"alignment\": null, \"anno\": {\"anno_select\": \"history\", \"__current_case__\": 2, \"reference_gene_sets\": null}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"extended_parameters\": {\"gff_feature_type\": \"exon\", \"gff_feature_attribute\": \"transcript_id\", \"summarization_level\": \"false\", \"multifeatures\": {\"multifeat\": \"\", \"__current_case__\": 0}, \"mapping_quality\": \"0\", \"exon_exon_junction_read_counting_enabled\": {\"count_exon_exon_junction_reads\": \"false\", \"__current_case__\": 1}, \"long_reads\": \"false\", \"by_read_group\": \"false\", \"largest_overlap\": \"false\", \"min_overlap\": \"1\", \"frac_overlap\": \"0\", \"frac_overlap_feature\": \"0\", \"read_extension_5p\": \"0\", \"read_extension_3p\": \"0\", \"read_reduction\": \"\", \"primary\": \"false\", \"ignore_dup\": \"false\", \"R\": \"false\", \"count_split_alignments_only\": \"false\"}, \"format\": \"tabdel_short\", \"include_feature_length_file\": \"false\", \"pe_parameters\": {\"fragment_counting_enabled\": {\"fragment_counting\": \" -p\", \"__current_case__\": 0, \"check_distance_enabled\": {\"check_distance\": \"false\", \"__current_case__\": 1}}, \"only_both_ends\": \"false\", \"exclude_chimerics\": \"true\"}, \"strand_specificity\": \"1\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.0.1",
            "type": "tool",
            "uuid": "25f079e2-2f9a-4a2d-9310-0cf6c4f92489",
            "workflow_outputs": []
        },
        "51": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/deseq2/deseq2/2.11.40.6+galaxy1",
            "errors": null,
            "id": 51,
            "input_connections": {
                "select_data|rep_factorName_0|rep_factorLevel_0|countsFile": [
                    {
                        "id": 47,
                        "output_name": "output_short"
                    },
                    {
                        "id": 48,
                        "output_name": "output_short"
                    }
                ],
                "select_data|rep_factorName_0|rep_factorLevel_1|countsFile": [
                    {
                        "id": 49,
                        "output_name": "output_short"
                    },
                    {
                        "id": 50,
                        "output_name": "output_short"
                    }
                ]
            },
            "inputs": [],
            "label": null,
            "name": "DESeq2",
            "outputs": [
                {
                    "name": "deseq_out",
                    "type": "tabular"
                },
                {
                    "name": "plots",
                    "type": "pdf"
                },
                {
                    "name": "counts_out",
                    "type": "tabular"
                }
            ],
            "position": {
                "left": 1550,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/deseq2/deseq2/2.11.40.6+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "6a3a025714d3",
                "name": "deseq2",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"tabular\", \"auto_mean_filter_off\": \"false\", \"batch_factors\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"esf\": \"\", \"fit_type\": \"1\", \"header\": \"true\", \"many_contrasts\": \"false\", \"normCounts\": \"true\", \"normRLog\": \"false\", \"normVST\": \"false\", \"outlier_filter_off\": \"false\", \"outlier_replace_off\": \"false\", \"pdf\": \"true\", \"select_data\": {\"how\": \"datasets_per_level\", \"__current_case__\": 1, \"rep_factorName\": [{\"__index__\": 0, \"factorName\": \"FactorName\", \"rep_factorLevel\": [{\"__index__\": 0, \"factorLevel\": \"G1E\", \"countsFile\": null}, {\"__index__\": 1, \"factorLevel\": \"Mega\", \"countsFile\": null}]}]}, \"tximport\": {\"tximport_selector\": \"count\", \"__current_case__\": 1}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.11.40.6+galaxy1",
            "type": "tool",
            "uuid": "a6dc5313-4cc9-421a-9dfa-72b0b09f7f43",
            "workflow_outputs": []
        },
        "52": {
            "annotation": "",
            "content_id": "Filter1",
            "errors": null,
            "id": 52,
            "input_connections": {
                "input": {
                    "id": 51,
                    "output_name": "deseq_out"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Filter",
            "outputs": [
                {
                    "name": "out_file1",
                    "type": "input"
                }
            ],
            "position": {
                "left": 1770,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "Filter1",
            "tool_state": "{\"__input_ext\": \"tabular\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"cond\": \"c7<0.01\", \"header_lines\": \"0\", \"input\": null, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.1.1",
            "type": "tool",
            "uuid": "60b8ec43-d31a-48c3-8da7-94d0bcc86d46",
            "workflow_outputs": []
        },
        "53": {
            "annotation": "",
            "content_id": "Filter1",
            "errors": null,
            "id": 53,
            "input_connections": {
                "input": {
                    "id": 52,
                    "output_name": "out_file1"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Filter",
            "outputs": [
                {
                    "name": "out_file1",
                    "type": "input"
                }
            ],
            "position": {
                "left": 1990,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "Filter1",
            "tool_state": "{\"__input_ext\": \"tabular\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"cond\": \"c3>0\", \"header_lines\": \"0\", \"input\": null, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.1.1",
            "type": "tool",
            "uuid": "5d787885-182b-4c25-b035-2cf4592e4f62",
            "workflow_outputs": []
        },
        "54": {
            "annotation": "",
            "content_id": "Filter1",
            "errors": null,
            "id": 54,
            "input_connections": {
                "input": {
                    "id": 52,
                    "output_name": "out_file1"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Filter",
            "outputs": [
                {
                    "name": "out_file1",
                    "type": "input"
                }
            ],
            "position": {
                "left": 1990,
                "top": 130
            },
            "post_job_actions": {},
            "tool_id": "Filter1",
            "tool_state": "{\"__input_ext\": \"tabular\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm10.len\", \"cond\": \"c3<0\", \"header_lines\": \"0\", \"input\": null, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.1.1",
            "type": "tool",
            "uuid": "27499601-6f86-4947-9796-4002828fae9d",
            "workflow_outputs": []
        }
    },
    "tags": [],
    "uuid": "6eaebc1c-f62d-4c31-8b1e-1d464ea43e82",
    "version": 0
}
```
