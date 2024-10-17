# Molecular-Weight-of-Genome-Enzyme
EgCompBio Diploma

<svg xmlns="http://www.w3.org/2000/svg" width="256" height="256" fill="none" viewBox="0 0 256 256"><rect width="256" height="256" fill="#242938" rx="60"/><path fill="url(#paint0_linear_2_47)" d="M127.279 29C76.5066 29 79.6772 51.018 79.6772 51.018L79.7338 73.8284H128.185V80.6772H60.4893C60.4893 80.6772 28 76.9926 28 128.222C28 179.452 56.3573 177.636 56.3573 177.636H73.2812V153.863C73.2812 153.863 72.369 125.506 101.186 125.506H149.24C149.24 125.506 176.239 125.942 176.239 99.4123V55.5461C176.239 55.5461 180.338 29 127.279 29ZM100.563 44.339C105.384 44.339 109.28 48.2351 109.28 53.0556C109.28 57.8761 105.384 61.7723 100.563 61.7723C95.7426 61.7723 91.8465 57.8761 91.8465 53.0556C91.8465 48.2351 95.7426 44.339 100.563 44.339Z"/><path fill="url(#paint1_linear_2_47)" d="M128.721 227.958C179.493 227.958 176.323 205.941 176.323 205.941L176.266 183.13H127.815V176.281H195.511C195.511 176.281 228 179.966 228 128.736C228 77.5062 199.643 79.323 199.643 79.323H182.719V103.096C182.719 103.096 183.631 131.453 154.814 131.453H106.76C106.76 131.453 79.7607 131.016 79.7607 157.546V201.412C79.7607 201.412 75.6615 227.958 128.721 227.958ZM155.437 212.619C150.616 212.619 146.72 208.723 146.72 203.903C146.72 199.082 150.616 195.186 155.437 195.186C160.257 195.186 164.154 199.082 164.154 203.903C164.154 208.723 160.257 212.619 155.437 212.619Z"/><defs><linearGradient id="paint0_linear_2_47" x1="47.22" x2="146.333" y1="46.896" y2="145.02" gradientUnits="userSpaceOnUse"><stop stop-color="#387EB8"/><stop offset="1" stop-color="#366994"/></linearGradient><linearGradient id="paint1_linear_2_47" x1="108.056" x2="214.492" y1="109.905" y2="210.522" gradientUnits="userSpaceOnUse"><stop stop-color="#FFE052"/><stop offset="1" stop-color="#FFC331"/></linearGradient></defs></svg>
![python](https://github.com/user-attachments/assets/9444fa14-9129-4e0c-97a5-5fe1a81a663d)
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



