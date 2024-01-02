# Graph-based Table Representation Learning (GTRL)
The objective of the proposed Table Representation Learning is to develop methods for learning table entry embeddings that are sensitive to the semantic meanings of the entries, while  preserving table-parsing-friendly features, such as permutation invariance. 

__We are in the process of updating the functions to align with the revised terminology/concept used in the paper. Consequently, we will be gradually updating this repository with our source code and documentation.__


<div style="text-align: center">
    <img src="https://github.com/DIMA-VUB/Graph-based_Table_Representation_Learning/blob/main/adhesive_dataset/design_34.jpg?raw=true">
</div>


## News
`31/12/2023`: Initial version of the Graph-based Table Representation Learning (GTRL) project is released. Especially the dataset of the industrial document used  to evaluate the proposed method.


# Dataset

Existing table datasets are predominantly compiled towards table structure recognition, resulting in a lack of datasets that can be employed for our for **Table Representation Learning** where the availability of per-entry semantic labeling is vital.

We therefore had to create a new dataset which could emerge from a joint collaboration between our research group and an industrial partner, Flanders Make, who targets an intelligent information extraction from industrial documents. They realized that current methods fall short in realizing their goal. Their documents typically feature complex table layouts and are content-rich using specialized terms and symbols, each carrying a domain-specific meaning. As domain experts, Flanders Make helped us to create the ground truth for the table semantic label (TSL) in our dataset. Variety within 100 annotated tables from 78 adhesive datasheets is described below:

<table>
    <tr>
        <td></td>
        <td><b>min</b></td>
        <td><b>max</b></td>
        <td><b>average</b></td>
    </tr>
    <tr>
        <td>Number of rows</td>
        <td>1</td>
        <td>25</td>
        <td>4.81</td>
    </tr>
    <tr>
        <td>Number of columns</td>
        <td>1</td>
        <td>10</td>
        <td>2.57</td>
    </tr>
    <tr>
        <td>Class distribution of TSL</td>
        <td>3</td>
        <td>457</td>
        <td>115.8</td>
    </tr>
    <tr>
        <td>Number of HGT nodes</td>
        <td>4</td>
        <td>59</td>
        <td>20.57</td>
    </tr>
</table>



In short, we conceptualize intelligent information extraction from tables (or semi-structured data) as encompassing three phases: Table Structure Recognition, Table Representation Learning and a Fine-tuning phase for downstream tasks. Table Representation Learning is the central focus of our current work and it is underrepresented in current Large Language Model efforts. We merely see table processing finetuned to the context of specific downstream tasks. In our work, we strive to develop a generic methodology (not tuned to a specific task or dataset) to understand the rich information hidden within tables.


The adhesive dataset  folder is structured as follows:
- ["The collected PDFs document about ahesive datasheets"](https://github.com/DIMA-VUB/Graph-based_Table_Representation_Learning/tree/d0cd88e5c841baf8dc97076fa94ef5c4f82dccd2/adhesive_dataset/AdhesiveMaterialsPDF). 
- ["the per table annotation with the format describe below"](https://github.com/DIMA-VUB/Graph-based_Table_Representation_Learning/tree/d0cd88e5c841baf8dc97076fa94ef5c4f82dccd2/adhesive_dataset/tableDataset)
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
- ["The corresponding Heteregenous  Graph Table (HGT) saved with gpickle using networkx"](https://github.com/DIMA-VUB/Graph-based_Table_Representation_Learning/tree/d0cd88e5c841baf8dc97076fa94ef5c4f82dccd2/adhesive_dataset/HeterogeneousGraphTable_HGT-format)
- [The visualization of each table crop extracted from the PDF  alongside its corresponding HGT format](https://github.com/DIMA-VUB/Graph-based_Table_Representation_Learning/tree/d0cd88e5c841baf8dc97076fa94ef5c4f82dccd2/adhesive_dataset)

<div style="text-align: center">
    <img src="https://github.com/DIMA-VUB/Graph-based_Table_Representation_Learning/blob/main/adhesive_dataset/4a580a1f-3127-473c-9f15-e3f9abc0f465.png?raw=true" width="50%" height="50%">
</div>


## Evaluation Metrics


## Replicabilty and reproducibilty 
ASAP
```
```

## Model Training
ASAP


## Citing
Our work can be cited using:

