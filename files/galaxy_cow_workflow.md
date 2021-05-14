### BED file
0-based [BED file](/files/cow_SNPs.bed) with the 3 SNPs described in [PMID 25772133](https://pubmed.ncbi.nlm.nih.gov/25772133/)

### BED Visualized via UCSC
![UCSC_cow](/files/cow_SNPs_UCSC.png)

### Intersect via Galaxy
```java
{
    "a_galaxy_workflow": "true",
    "annotation": "",
    "format-version": "0.1",
    "name": "cow_SNPs_intersect",
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
                    "name": "ERR181582a.sam"
                }
            ],
            "label": "ERR181582a.sam",
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
            "uuid": "309e1ff0-d3e9-4544-b804-ca138ff9d4c8",
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
                    "name": "saccer3_genes_chrI.gtf"
                }
            ],
            "label": "saccer3_genes_chrI.gtf",
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
            "uuid": "416a7247-5271-4969-bae9-01ac2baac31d",
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
                    "name": "chr1_part2.bed"
                }
            ],
            "label": "chr1_part2.bed",
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
            "uuid": "130af9ea-b1c0-451d-ae0c-88400b0c88b0",
            "workflow_outputs": []
        },
        "3": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/intersect/gops_intersect_1/1.0.0",
            "errors": null,
            "id": 3,
            "input_connections": {
                "input1": {
                    "id": 1,
                    "output_name": "output"
                },
                "input2": {
                    "id": 0,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Intersect",
            "outputs": [
                {
                    "name": "output",
                    "type": "input"
                }
            ],
            "position": {
                "left": 230,
                "top": 10
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/intersect/gops_intersect_1/1.0.0",
            "tool_shed_repository": {
                "changeset_revision": "33b3f3688db4",
                "name": "intersect",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bed\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/?.len\", \"input1\": null, \"input2\": null, \"min\": \"1\", \"returntype\": \"\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.0.0",
            "type": "tool",
            "uuid": "58e7bf1d-e67f-49a8-abe0-6f8dc3357da2",
            "workflow_outputs": []
        },
        "4": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/intersect/gops_intersect_1/1.0.0",
            "errors": null,
            "id": 4,
            "input_connections": {
                "input1": {
                    "id": 0,
                    "output_name": "output"
                },
                "input2": {
                    "id": 1,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Intersect",
            "outputs": [
                {
                    "name": "output",
                    "type": "input"
                }
            ],
            "position": {
                "left": 230,
                "top": 250
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/intersect/gops_intersect_1/1.0.0",
            "tool_shed_repository": {
                "changeset_revision": "33b3f3688db4",
                "name": "intersect",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"interval\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/?.len\", \"input1\": null, \"input2\": null, \"min\": \"1\", \"returntype\": \"\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.0.0",
            "type": "tool",
            "uuid": "70536a78-a6ff-4991-97a3-0ebaed0be2f4",
            "workflow_outputs": []
        },
        "5": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/intersect/gops_intersect_1/1.0.0",
            "errors": null,
            "id": 5,
            "input_connections": {
                "input1": {
                    "id": 2,
                    "output_name": "output"
                },
                "input2": {
                    "id": 0,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Intersect",
            "outputs": [
                {
                    "name": "output",
                    "type": "input"
                }
            ],
            "position": {
                "left": 230,
                "top": 130
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/intersect/gops_intersect_1/1.0.0",
            "tool_shed_repository": {
                "changeset_revision": "33b3f3688db4",
                "name": "intersect",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"bed\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/?.len\", \"input1\": null, \"input2\": null, \"min\": \"1\", \"returntype\": \"\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.0.0",
            "type": "tool",
            "uuid": "1b7aecb5-be21-4bd6-834e-2e822766cf81",
            "workflow_outputs": []
        },
        "6": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/intersect/gops_intersect_1/1.0.0",
            "errors": null,
            "id": 6,
            "input_connections": {
                "input1": {
                    "id": 0,
                    "output_name": "output"
                },
                "input2": {
                    "id": 2,
                    "output_name": "output"
                }
            },
            "inputs": [],
            "label": null,
            "name": "Intersect",
            "outputs": [
                {
                    "name": "output",
                    "type": "input"
                }
            ],
            "position": {
                "left": 230,
                "top": 370
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/devteam/intersect/gops_intersect_1/1.0.0",
            "tool_shed_repository": {
                "changeset_revision": "33b3f3688db4",
                "name": "intersect",
                "owner": "devteam",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"__input_ext\": \"interval\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/?.len\", \"input1\": null, \"input2\": null, \"min\": \"1\", \"returntype\": \"\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.0.0",
            "type": "tool",
            "uuid": "7e1abf75-bd7b-4d4d-85ec-eec3ebe6e2fb",
            "workflow_outputs": []
        }
    },
    "tags": [],
    "uuid": "cc8b4246-6268-46af-8a48-ecda00984412",
    "version": 0
}
```
