### IGV Visualization
![output](/files/MOUSE_ChIP_IGV.png)

### Galaxy Workflow
1. FASTQ Froomer
2. Trummomatic
3. BWA Alignment
4. MACS2 callpeak

```json
{
    "a_galaxy_workflow": "true",
    "annotation": "",
    "format-version": "0.1",
    "name": "MOUSE_ChIP",
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
                    "name": "Mouse_ChIP-Seq_Example_Experimental_Data_chr19_mm9.fastq"
                }
            ],
            "label": "Mouse_ChIP-Seq_Example_Experimental_Data_chr19_mm9.fastq",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "bottom": 294.3055648803711,
                "height": 101.31945037841797,
                "left": 236.9965362548828,
                "right": 436.9965515136719,
                "top": 192.98611450195312,
                "width": 200.00001525878906,
                "x": 236.9965362548828,
                "y": 192.98611450195312
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "5d10c937-8d38-4536-99fa-3b54b79691b3",
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "output",
                    "uuid": "e5854ba6-03ac-40ea-9887-f4e2dc193031"
                }
            ]
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
                    "name": "Mouse_ChIP-Seq_example_Control_Data_chr19_mm9.fastq"
                }
            ],
            "label": "Mouse_ChIP-Seq_example_Control_Data_chr19_mm9.fastq",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "bottom": 414.3055648803711,
                "height": 101.31945037841797,
                "left": 236.9965362548828,
                "right": 436.9965515136719,
                "top": 312.9861145019531,
                "width": 200.00001525878906,
                "x": 236.9965362548828,
                "y": 312.9861145019531
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "741dcb18-5e96-43c6-824e-d8f2ea845911",
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "output",
                    "uuid": "0652c9b5-9e2b-4038-b36d-e17c72ce945f"
                }
            ]
        },
        "2": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastq_groomer/fastq_groomer/1.1.5",
            "errors": null,
            "id": 2,
            "input_connections": {
                "input_file": {
                    "id": 0,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "FASTQ Groomer",
            "outputs": [
                {
                    "name": "output_file",
                    "type": "fastqsanger"
                }
            ],
            "position": {
                "bottom": 485.41668701171875,
                "height": 292.4305725097656,
                "left": 456.9965515136719,
                "right": 656.9965667724609,
                "top": 192.98611450195312,
                "width": 200.00001525878906,
                "x": 456.9965515136719,
                "y": 192.98611450195312
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastq_groomer/fastq_groomer/1.1.5",
            "tool_shed_repository": {
                "changeset_revision": "47e5dbc3e790",
                "name": "fastq_groomer",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastq\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm9.len\", \"input_file\": {\"__class__\": \"ConnectedValue\"}, \"input_type\": \"sanger\", \"options_type\": {\"options_type_selector\": \"basic\", \"__current_case__\": 0}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.1.5",
            "type": "tool",
            "uuid": "712f8496-877e-4707-97f6-6661c9205453",
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "output_file",
                    "uuid": "ec81d867-6f9e-4acc-80d3-147cf5e54c31"
                }
            ]
        },
        "3": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastq_groomer/fastq_groomer/1.1.5",
            "errors": null,
            "id": 3,
            "input_connections": {
                "input_file": {
                    "id": 1,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "FASTQ Groomer",
            "outputs": [
                {
                    "name": "output_file",
                    "type": "fastqsanger"
                }
            ],
            "position": {
                "bottom": 605.4166870117188,
                "height": 292.4305725097656,
                "left": 456.9965515136719,
                "right": 656.9965667724609,
                "top": 312.9861145019531,
                "width": 200.00001525878906,
                "x": 456.9965515136719,
                "y": 312.9861145019531
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastq_groomer/fastq_groomer/1.1.5",
            "tool_shed_repository": {
                "changeset_revision": "47e5dbc3e790",
                "name": "fastq_groomer",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastq\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm9.len\", \"input_file\": {\"__class__\": \"ConnectedValue\"}, \"input_type\": \"sanger\", \"options_type\": {\"options_type_selector\": \"basic\", \"__current_case__\": 0}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.1.5",
            "type": "tool",
            "uuid": "2672fe9b-3512-4210-83fe-97a19f593be0",
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "output_file",
                    "uuid": "9661d918-803b-4d81-b75a-839b33c8bd09"
                }
            ]
        },
        "4": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 4,
            "input_connections": {
                "input_file": {
                    "id": 2,
                    "output_name": "output_file"
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
                "bottom": 505.41668701171875,
                "height": 312.4305725097656,
                "left": 676.99658203125,
                "right": 876.9965972900391,
                "top": 192.98611450195312,
                "width": 200.00001525878906,
                "x": 676.99658203125,
                "y": 192.98611450195312
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm9.len\", \"contaminants\": null, \"input_file\": {\"__class__\": \"ConnectedValue\"}, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "681a42db-96d5-4552-84c8-f1b617192d50",
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "html_file",
                    "uuid": "1df473df-8874-4df4-bd71-12397fb76f54"
                },
                {
                    "label": null,
                    "output_name": "text_file",
                    "uuid": "65d22216-6531-4c2f-809c-ccfc7fb49bdf"
                }
            ]
        },
        "5": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "errors": null,
            "id": 5,
            "input_connections": {
                "readtype|fastq_in": {
                    "id": 2,
                    "output_name": "output_file"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Trimmomatic",
            "outputs": [
                {
                    "name": "fastq_out",
                    "type": "input"
                }
            ],
            "position": {
                "bottom": 525.4167022705078,
                "height": 92.43055725097656,
                "left": 676.99658203125,
                "right": 876.9965972900391,
                "top": 432.98614501953125,
                "width": 200.00001525878906,
                "x": 676.99658203125,
                "y": 432.98614501953125
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "tool_shed_repository": {
                "changeset_revision": "898b67846b47",
                "name": "trimmomatic",
                "owner": "pjbriggs",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"__job_resource\": {\"__job_resource__select\": \"no\", \"__current_case__\": 0}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm9.len\", \"illuminaclip\": {\"do_illuminaclip\": \"false\", \"__current_case__\": 1}, \"operations\": [{\"__index__\": 0, \"operation\": {\"name\": \"SLIDINGWINDOW\", \"__current_case__\": 0, \"window_size\": \"4\", \"required_quality\": \"20\"}}], \"output_err\": \"false\", \"output_logs\": \"false\", \"readtype\": {\"single_or_paired\": \"se\", \"__current_case__\": 0, \"fastq_in\": {\"__class__\": \"ConnectedValue\"}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.38.0",
            "type": "tool",
            "uuid": "b5eaa22a-3380-4630-853d-d9073b30142c",
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "fastq_out",
                    "uuid": "5cf684b2-daf7-46c1-9e80-d3bc33db17bc"
                }
            ]
        },
        "6": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "errors": null,
            "id": 6,
            "input_connections": {
                "readtype|fastq_in": {
                    "id": 3,
                    "output_name": "output_file"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Trimmomatic",
            "outputs": [
                {
                    "name": "fastq_out",
                    "type": "input"
                }
            ],
            "position": {
                "bottom": 405.4166717529297,
                "height": 92.43055725097656,
                "left": 676.99658203125,
                "right": 876.9965972900391,
                "top": 312.9861145019531,
                "width": 200.00001525878906,
                "x": 676.99658203125,
                "y": 312.9861145019531
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/pjbriggs/trimmomatic/trimmomatic/0.38.0",
            "tool_shed_repository": {
                "changeset_revision": "898b67846b47",
                "name": "trimmomatic",
                "owner": "pjbriggs",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"__job_resource\": {\"__job_resource__select\": \"no\", \"__current_case__\": 0}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm9.len\", \"illuminaclip\": {\"do_illuminaclip\": \"false\", \"__current_case__\": 1}, \"operations\": [{\"__index__\": 0, \"operation\": {\"name\": \"SLIDINGWINDOW\", \"__current_case__\": 0, \"window_size\": \"4\", \"required_quality\": \"20\"}}], \"output_err\": \"false\", \"output_logs\": \"false\", \"readtype\": {\"single_or_paired\": \"se\", \"__current_case__\": 0, \"fastq_in\": {\"__class__\": \"ConnectedValue\"}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.38.0",
            "type": "tool",
            "uuid": "67115b62-5f6e-4b0d-bca6-f425e9ee4428",
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "fastq_out",
                    "uuid": "fbb554e6-c146-4efd-b6de-113c4868e72c"
                }
            ]
        },
        "7": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 7,
            "input_connections": {
                "input_file": {
                    "id": 3,
                    "output_name": "output_file"
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
                "bottom": 865.4167175292969,
                "height": 312.4305725097656,
                "left": 676.99658203125,
                "right": 876.9965972900391,
                "top": 552.9861450195312,
                "width": 200.00001525878906,
                "x": 676.99658203125,
                "y": 552.9861450195312
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm9.len\", \"contaminants\": null, \"input_file\": {\"__class__\": \"ConnectedValue\"}, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "4cad8c0e-3b94-4c24-b516-84fd4e75bb35",
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "html_file",
                    "uuid": "0044de21-4816-4d00-bd64-8f9709dc4665"
                },
                {
                    "label": null,
                    "output_name": "text_file",
                    "uuid": "8a034dce-7f13-455b-8256-22fea9d2b12f"
                }
            ]
        },
        "8": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 8,
            "input_connections": {
                "input_file": {
                    "id": 5,
                    "output_name": "fastq_out"
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
                "bottom": 625.4166870117188,
                "height": 312.4305725097656,
                "left": 896.99658203125,
                "right": 1096.996597290039,
                "top": 312.9861145019531,
                "width": 200.00001525878906,
                "x": 896.99658203125,
                "y": 312.9861145019531
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm9.len\", \"contaminants\": null, \"input_file\": {\"__class__\": \"ConnectedValue\"}, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "c8c86c00-d9b0-4fb3-835f-82318564b749",
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "html_file",
                    "uuid": "2f208ff1-353a-4192-99af-f2aff0038d0e"
                },
                {
                    "label": null,
                    "output_name": "text_file",
                    "uuid": "9d5c5250-aabf-496e-90b4-2eb4eb3ab5cf"
                }
            ]
        },
        "9": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/bwa/bwa/0.7.17.4",
            "errors": null,
            "id": 9,
            "input_connections": {
                "input_type|fastq_input1": {
                    "id": 5,
                    "output_name": "fastq_out"
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
                "bottom": 685.4167022705078,
                "height": 132.43055725097656,
                "left": 896.99658203125,
                "right": 1096.996597290039,
                "top": 552.9861450195312,
                "width": 200.00001525878906,
                "x": 896.99658203125,
                "y": 552.9861450195312
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/bwa/bwa/0.7.17.4",
            "tool_shed_repository": {
                "changeset_revision": "3fe632431b68",
                "name": "bwa",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"__job_resource\": {\"__job_resource__select\": \"no\", \"__current_case__\": 0}, \"analysis_type\": {\"analysis_type_selector\": \"illumina\", \"__current_case__\": 0}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm9.len\", \"input_type\": {\"input_type_selector\": \"single\", \"__current_case__\": 2, \"fastq_input1\": {\"__class__\": \"ConnectedValue\"}, \"adv_se_options\": {\"adv_se_options_selector\": \"do_not_set\", \"__current_case__\": 1}}, \"reference_source\": {\"reference_source_selector\": \"cached\", \"__current_case__\": 0, \"ref_file\": \"mm9\"}, \"rg\": {\"rg_selector\": \"do_not_set\", \"__current_case__\": 3}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.7.17.4",
            "type": "tool",
            "uuid": "659c9e35-ab54-4e5a-a5c2-46f630713c06",
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "bam_output",
                    "uuid": "b07ca922-af8d-40bc-ab80-ac4e7e3b21fb"
                }
            ]
        },
        "10": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "errors": null,
            "id": 10,
            "input_connections": {
                "input_file": {
                    "id": 6,
                    "output_name": "fastq_out"
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
                "bottom": 505.41668701171875,
                "height": 312.4305725097656,
                "left": 896.99658203125,
                "right": 1096.996597290039,
                "top": 192.98611450195312,
                "width": 200.00001525878906,
                "x": 896.99658203125,
                "y": 192.98611450195312
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/fastqc/fastqc/0.72+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "e7b2202befea",
                "name": "fastqc",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"adapters\": null, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm9.len\", \"contaminants\": null, \"input_file\": {\"__class__\": \"ConnectedValue\"}, \"kmers\": \"7\", \"limits\": null, \"min_length\": null, \"nogroup\": \"false\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.72+galaxy1",
            "type": "tool",
            "uuid": "22e0256a-d5e9-4be2-b092-66b6cdd763b2",
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "html_file",
                    "uuid": "b11841d3-596b-4868-bf45-ab270bde9c18"
                },
                {
                    "label": null,
                    "output_name": "text_file",
                    "uuid": "01e3b536-dd99-4698-8f2d-0a1937ada039"
                }
            ]
        },
        "11": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/bwa/bwa/0.7.17.4",
            "errors": null,
            "id": 11,
            "input_connections": {
                "input_type|fastq_input1": {
                    "id": 6,
                    "output_name": "fastq_out"
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
                "bottom": 565.4167022705078,
                "height": 132.43055725097656,
                "left": 896.99658203125,
                "right": 1096.996597290039,
                "top": 432.98614501953125,
                "width": 200.00001525878906,
                "x": 896.99658203125,
                "y": 432.98614501953125
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/bwa/bwa/0.7.17.4",
            "tool_shed_repository": {
                "changeset_revision": "3fe632431b68",
                "name": "bwa",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"fastqsanger\", \"__job_resource\": {\"__job_resource__select\": \"no\", \"__current_case__\": 0}, \"analysis_type\": {\"analysis_type_selector\": \"illumina\", \"__current_case__\": 0}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm9.len\", \"input_type\": {\"input_type_selector\": \"single\", \"__current_case__\": 2, \"fastq_input1\": {\"__class__\": \"ConnectedValue\"}, \"adv_se_options\": {\"adv_se_options_selector\": \"do_not_set\", \"__current_case__\": 1}}, \"reference_source\": {\"reference_source_selector\": \"cached\", \"__current_case__\": 0, \"ref_file\": \"mm9\"}, \"rg\": {\"rg_selector\": \"do_not_set\", \"__current_case__\": 3}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.7.17.4",
            "type": "tool",
            "uuid": "3aabfd25-cd73-4f3c-b0dc-d6b551a0012f",
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "bam_output",
                    "uuid": "71e0420f-284d-4b99-8db9-460bf3563712"
                }
            ]
        },
        "12": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/macs2/macs2_callpeak/2.1.1.20160309.6",
            "errors": null,
            "id": 12,
            "input_connections": {
                "control|c_multiple|input_control_file": {
                    "id": 11,
                    "output_name": "bam_output"
                },
                "treatment|input_treatment_file": {
                    "id": 9,
                    "output_name": "bam_output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "MACS2 callpeak",
            "outputs": [
                {
                    "name": "output_tabular",
                    "type": "tabular"
                },
                {
                    "name": "output_narrowpeaks",
                    "type": "bed"
                },
                {
                    "name": "output_treat_pileup",
                    "type": "bedgraph"
                },
                {
                    "name": "output_control_lambda",
                    "type": "bedgraph"
                }
            ],
            "position": {
                "bottom": 605.4166870117188,
                "height": 412.4305725097656,
                "left": 1116.99658203125,
                "right": 1316.996597290039,
                "top": 192.98611450195312,
                "width": 200.00001525878906,
                "x": 1116.99658203125,
                "y": 192.98611450195312
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/macs2/macs2_callpeak/2.1.1.20160309.6",
            "tool_shed_repository": {
                "changeset_revision": "424aefbd7777",
                "name": "macs2",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"input\", \"advanced_options\": {\"to_large\": \"false\", \"nolambda\": \"false\", \"spmr\": \"false\", \"ratio\": null, \"slocal\": null, \"llocal\": null, \"broad_options\": {\"broad_options_selector\": \"nobroad\", \"__current_case__\": 1, \"call_summits\": \"false\"}, \"keep_dup_options\": {\"keep_dup_options_selector\": \"1\", \"__current_case__\": 1}}, \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/mm9.len\", \"control\": {\"c_select\": \"Yes\", \"__current_case__\": 0, \"c_multiple\": {\"c_multi_select\": \"No\", \"__current_case__\": 0, \"input_control_file\": {\"__class__\": \"ConnectedValue\"}}}, \"cutoff_options\": {\"cutoff_options_selector\": \"qvalue\", \"__current_case__\": 1, \"qvalue\": \"0.05\"}, \"effective_genome_size_options\": {\"effective_genome_size_options_selector\": \"1870000000\", \"__current_case__\": 1}, \"format\": \"BAM\", \"nomodel_type\": {\"nomodel_type_selector\": \"create_model\", \"__current_case__\": 0, \"mfold_lower\": \"5\", \"mfold_upper\": \"50\", \"band_width\": \"300\"}, \"outputs\": [\"peaks_tabular\", \"bdg\"], \"treatment\": {\"t_multi_select\": \"No\", \"__current_case__\": 0, \"input_treatment_file\": {\"__class__\": \"ConnectedValue\"}}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.1.1.20160309.6",
            "type": "tool",
            "uuid": "6eaa5bc9-482b-4fe4-ab1f-0602a52c8867",
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "output_tabular",
                    "uuid": "0f953eb7-b08a-4ff3-9ed3-9a3574c4a81d"
                },
                {
                    "label": null,
                    "output_name": "output_narrowpeaks",
                    "uuid": "6ee31c69-25a8-413a-a9ae-5053b5cf3303"
                },
                {
                    "label": null,
                    "output_name": "output_treat_pileup",
                    "uuid": "db0821f8-76a1-4073-a7e7-441c95b08c0f"
                },
                {
                    "label": null,
                    "output_name": "output_control_lambda",
                    "uuid": "bdf2a1ca-8bee-4d54-9e9a-45a6b93e5cbe"
                }
            ]
        }
    },
    "tags": [],
    "uuid": "145e822f-25e6-4436-8b11-207e434eac65",
    "version": 1
}
```
