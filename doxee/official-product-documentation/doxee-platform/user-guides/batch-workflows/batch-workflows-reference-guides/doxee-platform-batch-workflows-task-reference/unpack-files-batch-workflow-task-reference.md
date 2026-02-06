---
id: "69cb72b3-5914-4623-8d27-e876f0bd5273"
title: "Unpack Files Batch Workflow Task Reference"
slug: "unpack-files-batch-workflow-task-reference"
category: "Doxee Platform Batch Workflows Task Reference"
category_path:
  - "Product guides"
  - "Batch Workflows"
  - "Batch Workflows Reference Guides"
  - "Doxee Platform Batch Workflows Task Reference"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-08T11:00:47.724Z"
modified_at: "2025-12-17T18:16:11.636Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/unpack-files-batch-workflow-task-reference"
synced_at: "2026-01-28T20:49:09.532Z"
checksum: "a444cc19655a2245"
---

## Description
The **Unpack Files** task decompresses files, for example ZIP files, in order to make the files of the package available to the workflow.

> Note

The Unpack Files task uses 7-Zip archiver, which supports a large number of formats. The following archive formats have been tested on the development environment:

- 7z 

- XZ

- BZIP2 

- GZIP 

- TAR 

- ZIP 

- WIM 

- RAR 

- ARJ 

- ISO 

- CAB

For more information, see: [https://7-zip.org](https://7-zip.org/).

### Principles of operation
Eligible input files are processed in alphabetical order. Each eligible input file is unpacked with 7z. 

It is possible to process multiple archives in one input.

> Note

If several files with the same name are found during unpacking, only the first one will be processed and the others will be ignored.

## Configuration
**![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAWgAAAAvCAIAAABBrcfiAAAABmJLR0QA/wD/AP+gvaeTAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAEVElEQVR4nO3cT0hbBxwH8K8xodFIeWWQZiwV/0BsIWHohLY4d1gvErYe1jdGtoOHwWDq2EA9TMJoIZWBZgxW3Q6ug0ENYyqjB/GS0M6lGg8KdaOaOcPktX2+4gy2T1OtcQf/bBn+yXNbor7v55S8fN+PXy5f3nuE5KytrWFb8djo1BO702U1xceHpk+UV9gt2weJSG8MW6+k/it1Dc29v22+/z3Y+mlgdAF49OO3n7cNxLKyHhEdRMbNF1Kkf1Y4rt68E71U6kiJ2C629VzM+GJEdHBtXnHMRIJzFeKb1cuh4eg/InPBtoa6wASQkAa/aqn1iKLoqfMPKgAA5XZbnUcURc9HHZF4RjcnoqzZKA5pJKicdbnOuM49Hh6fSY2srszLivoUMBecdHqufhMIfOYRhroGogDGb34RKWvs6fnuy7qaYiHj2xNRVqwXhxS5pVQ4i5dXXig+rQRHpB3CguPFE0qop6s7FIO6vATgpP20afh6a2Bo3lpkzdjSRJRdBgCYiQRl0/QPl5s/bh2QTcqtyPbNoQy0vHc5uOJ8vf7SuY1D1porXW1vF8e6W97/IBBdzdTWRJRVBgDS2KDiqG291tl5rbOztdYhByMz20TjdyPR4xfE11z2JXXzcYYS/Vm1v+xp+cRjV8an+ZCDSB8MAEZvS9YK58adhtX5kk0JjkgoKTtrinZ9P7oVFSprqtHb/Jbo8U/mFwIA5mLB6x+Koig2BFS3p/q5LHwBIsq8nB1/AAZgdUVNmiym1CMrJos5NZZQ1VxLSoyIjrRdi4OIaDuGvSNERKlYHESkGYuDiDRjcRCRZsZwOJztHYjokDECqKqqyvYaRHRohMNh3qoQkWYsDiLSjMVBRJqxOIhIMxYHEWnG4iAizVgcRHr1LIFn+zyVxUGkTzJ+ysPg1/s7mcVBpEvRdjwFlr2IJvZxNouDSH+SMdz3w+CGQcZMB5KaB7A4iPRn0o9lG+w3YK/HajsmNf9dMIuDSGeSY5A6kNuEMgFl7yJXhtQBjfcrLA4infnFh6QNhfWIj+HRGRQ2IunFr7KmGSwOIj1JhPCgD8f8cMRxtwL3+uBowjHgQTsWNYxhcRDpyYQfKEfhG387ZEOhD/AjGkt/DIuDSDcW+jHbj3wfSswAkAPkmAGgpB75Nsz6sZDuJBYHkW5MeoHzKHIDAGxwjcK1fukhoKgJ6MC9oTQnsTiI9GGuG3+MocCHU+vvE5j2YXps49NT9SiwId6OubSGsTiI9CCByUbAjdJXdwiYUeoD+jARSmcci4NIBx7ewGMZghe2rUNmVPaisvyvjO0dCOV44sfDvecZ/4cdiehAiWPKC5yHZQlTu15QWNyIX8VUP5537z6RxUF01Kl3sCgDMu5fSCu/GILqhmW3CIuD6KizuPHKvIa/3jAKyNsr8u82IqLDIE/4b+fx4SgRacbiICLNWBxEpBmLg4g0Y3EQkWZGAOFwONtrENFh8ie08E/9QlMN0gAAAABJRU5ErkJggg==)**

In the **Alias **field, enter the name of the task that will be displayed in the workflow.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}