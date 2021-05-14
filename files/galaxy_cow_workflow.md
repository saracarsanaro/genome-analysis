### BED file
0-based [BED file](/files/cow_SNPs.bed) with the 3 SNPs described in [PMID 25772133](https://pubmed.ncbi.nlm.nih.gov/25772133/)

### BED Visualized via UCSC
![UCSC_cow](/files/cow_SNPs_UCSC.png)

### Intersect via Galaxy
```json
{
    "a_galaxy_workflow": "true",
    "annotation": "",
    "format-version": "0.1",
    "name": "cows_4",
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
                    "name": "cow_part4_1.bed"
                }
            ],
            "label": "cow_part4_1.bed",
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
            "uuid": "a8a85c81-be66-4bb2-949e-eb0b664dcc65",
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
                    "name": "cow_cfl_all_exons.bed"
                }
            ],
            "label": "cow_cfl_all_exons.bed",
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
            "uuid": "0db4a3e9-3e0d-4d14-b91b-399f6dfe6965",
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
                    "name": "cow_cfl_coding_exons.bed"
                }
            ],
            "label": "cow_cfl_coding_exons.bed",
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
            "uuid": "88893983-37b0-4aed-aa84-9a6e008754a4",
            "workflow_outputs": []
        },
        "3": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/devteam/intersect/gops_intersect_1/1.0.0",
            "errors": null,
            "id": 3,
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
            "tool_state": "{\"__input_ext\": \"interval\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/?.len\", \"input1\": null, \"input2\": null, \"min\": \"1\", \"returntype\": \"\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.0.0",
            "type": "tool",
            "uuid": "c8937180-0b0e-485f-b654-e3ecb72043d8",
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
            "tool_state": "{\"__input_ext\": \"interval\", \"chromInfo\": \"/cvmfs/data.galaxyproject.org/managed/len/ucsc/?.len\", \"input1\": null, \"input2\": null, \"min\": \"1\", \"returntype\": \"\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "1.0.0",
            "type": "tool",
            "uuid": "103a84e5-429b-4553-bdef-423b59cda56e",
            "workflow_outputs": []
        }
    },
    "tags": [],
    "uuid": "0bd462e8-f2e4-4e65-83f5-f2f3c8fb558e",
    "version": 0
}
```
