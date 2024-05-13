# Graph-based Table Representation Learning (GTRL)

__We are in the process of updating the functions to align with the revised terminology/concept used in the paper. Consequently, we will soon release our source code and documentation.__

## News

`02/05/2024`: Extended results on the public TURL WIKITABLE dataset, associated with the code. Download the dataset and checkpoints ["here"](https://vub-my.sharepoint.com/:u:/g/personal/willy_carlos_tchuitcheu_vub_be/EUN8kWx9rEtJliHZQJcG8pkBmZbr16QdxmjpAEIp3Rvr8Q?e=6EkTwG).

`31/12/2023`: Initial version of the Graph-based Table Representation Learning (GTRL) project is released. Especially the new benchmarking table dataset of documents about adhesive material. ["You can download it here."](https://vub-my.sharepoint.com/:u:/g/personal/willy_carlos_tchuitcheu_vub_be/EV8e6IGYRrtFu46_NmBPK0QB-SEAs6-8QW6F9tDUESIzVw?e=7HbjfL)

# Our Dataset

The folder of the ["new dataset"](https://vub-my.sharepoint.com/:u:/g/personal/willy_carlos_tchuitcheu_vub_be/EV8e6IGYRrtFu46_NmBPK0QB-SEAs6-8QW6F9tDUESIzVw?e=7HbjfL) about adhesive is structured as follows:

- AdhesiveMaterialsPDF: the collection of PDF documents related to adhesive datasheets under /
- TableDataset: Annotation of each table following the JSON format described below:

```json
{
    "id-table": "0b6979f0-3ffe-431c-83c0-4b3ef6010d31", /*A unique ID assigned to each table, used as the filename. */
    "language": "ENGLISH",  /*The language of the PDF from which the table is extracted.*/
    "table-rect": "(531.7, 294.9, 1011.2, 245.6)", /* The bounding boxes of the table within the PDF, defined by the coordinates (x, y, width, height). */
    "PDF-name": "TDS_3M DP760", /* The name of the PDF file, located in the folder containing the adhesive datasheets.  */
    "Page-number": "2", /*The page number from which this table was extracted. */
    "Cells": [
        {
            "id-entry": 0,  /* The unique id of the cell whitin this table. Note that, this id is idexed and  node id  on the HGT)*/
            "entry-rect": "(544.8, 331.5, 925, 57.5)", /* The bounding boxes for each cell are specified by their (x, y, width, height) coordinates, which are not normalized relative to the table's overall width and height  */
            "table-semantic-label": "KEYWORD", /* The table semantic label is determined based on domain knowledge.  */
            "table-header": "Yes", /* Location of the cell, row-column header or not */
            "content": " Viscosity ", /* The text of the cell */
            "Relationships": {  /* Define relationships using the four cardinal directions - left, right, up, and down */
                "down": [1, 2, 4], /* This cell is identified as a merged cell due to its alignment with multiple cells extending downward. */
                "left": [6], /* The cell id 6 is on its left */
            }
        },
        ...
        // other cell's attributes
        ...
    ]
}
```

- HeterogeneousGraphTable_HGT-format: the Heterogenous Graph Table (HGT) format saved with gpickle extension using the python Networkx package."

- TABLE_TRAIN-TEST_SPLIT: contains ten random 80%-20% splits for training and testing, respectively, from which the average performance is reported in the study.

- CHECKPOINTS: This folder contains all the model checkpoints, organized by random split IDs.

<!-- ## Evaluation Metrics -->

## Replicabilty and reproducibilty

For our dataset (To be completed)

```bash
CUDA_VISIBLE_DEVICES=0,1  python3 main.py  --epochs 50 --root_directory "PATH/TO/THE/ADHESIVE_DATASET" -embed_dim 768 --num_hidden_layers 1 --num_attention_heads 12 --save_steps 500 --batch_size 256 --optimizer adam  --smp_target_dataset SMP_CTA_TASK_TSL 
```

For the TURL dataset:

```bash
CUDA_VISIBLE_DEVICES=0,1  python3 main_training_wikidataset_multi_label.py  --epochs 50 --root_directory "PATH/TO/THE/TURL_DATASET" -embed_dim 768 --num_hidden_layers 1 --num_attention_heads 12 --save_steps 500 --batch_size 256 --optimizer adam  --smp_target_dataset SMP_CTA_TASK_TSL 
```

## Model Training

We recommend  python3.9 and the necessary packages are listed in the requirements.txt file, while the packages for the entire virtual development environment are detailed in requirements.venv.txt

ASAP

## Citing

Our work can be cited using:
