# Molecular-Weight-of-Genome-Enzyme
EgCompBio Diploma

![Python](https://img.shields.io/badge/Language-Python-blue)

# import and install libraries

```python
!pip install BioPython
from Bio import SeqIO
from Bio.SeqUtils.ProtParam import ProteinAnalysis
from Bio.SeqUtils import molecular_weight
from Bio.Seq import Seq
from Bio.SeqUtils import ProtParam
import pandas as pd
```
# create function that calculate mw of one protein
```python
def get_molecular_weight(protein_sequence):
    analyzed_seq = ProteinAnalysis(protein_sequence)
    return analyzed_seq.molecular_weight()

# Example sequence
protein_sequence = "MKRISTTITTTITITTGNGAG"
print(get_molecular_weight(protein_sequence)/1000,"K Dalton")
```

# read fasta file path
```python

file_path=SeqIO.parse(protein fasta file path)
```
# create function to calculate mw for all proteins
```python

def calculate_molecular_weights (file_path):
 
    data = []   # create list to store data
    for record in SeqIO.parse(protein fasta file path):
        accession = record.id
        sequence = str(record.seq)
        prot_param = ProtParam.ProteinAnalysis(sequence)
        molecular_weight = prot_param.molecular_weight()
        data.append([accession, sequence, molecular_weight])
        

    df = pd.DataFrame(data, columns=['Accession', 'Sequence', 'MolecularWeight(dalton)'])  # create data frame to store variables
    return df
```
# calling function
```python
df = calculate_molecular_weights(file_path)
print(df)
```
# read PTT file
```python
pttfile=pd.read_csv(pttfile path)
```
# insert Locus tag to data frame
```python
df['Locus tag']=pttfile['Locus tag']
df
```
# create copy of data frame and drop column
```python
data_frame2=df.copy()
data_frame2=data_frame2.drop(['Accession', 'Sequence'], axis=1)
```



