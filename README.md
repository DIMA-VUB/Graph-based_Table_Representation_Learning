# Graph-based Table Representation Learning (GTRL)
The objective of the proposed Table Representation Learning is to develop methods for learning table entry embeddings that are sensitive to the semantic meanings of the entries, while  preserving table-parsing-friendly features, such as permutation invariance.



<div style="text-align: center">
    <img src="https://github.com/DIMA-VUB/Graph-based_Table_Representation_Learning/blob/main/adhesive_dataset/design_34.jpg?raw=true">
</div>


## News
`31/12/2023`: Initial version of the Graph-based Table Representation Learning (GTRL) project is released. Especially the dataset of the industrial document used  to evaluate the proposed method.


# Dataset
This new dataset emerges from a joint collaboration between our research group and an industrial partner, targeting intelligent information extraction from industrial documents. These documents typically feature complex table layouts and content-rich in specialized terms and symbols, each carrying substantial domain-specific meaning. This underscores the necessity of assigning each table entry a Table Semantic Label (TSL) relevant to the specific field.  We conceptualize modern intelligent information processing (Table or semi-structured data) as encompassing three phases: Table Structure Recognition, Table Representation Learning, and a Fine-tuning phase for downstream tasks. Historically underemphasized, Table Representation Learning is the central focus of our current work. In our work, we strive to refine our proposed methodology at an abstract level (not tune to a specific dataset) and employ the new dataset to validate several fundamental concepts we have introduced.



<div style="text-align: center">
    <img src="https://github.com/DIMA-VUB/Graph-based_Table_Representation_Learning/blob/main/adhesive_dataset/4a580a1f-3127-473c-9f15-e3f9abc0f465.png?raw=true" width="50%" height="50%">
</div>

Variety within 100 annotated tables from 78 adhesive datasheets:

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

## Evaluation Metrics


## Replicabilty and reproducibilty 
ASAP
```
```

## Model Training
ASAP


## Citing
Our work can be cited using:

