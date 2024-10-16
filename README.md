# Molecular-Weight-of-Genome-Enzyme
EgCompBio Diploma

# import and install libraries

'''r
!pip install BioPython
from Bio import SeqIO
from Bio.SeqUtils.ProtParam import ProteinAnalysis
from Bio.SeqUtils import molecular_weight
from Bio.Seq import Seq
from Bio.SeqUtils import ProtParam
import pandas as pd
'''
# create function that calculate mw of one protein

def get_molecular_weight(protein_sequence):
    analyzed_seq = ProteinAnalysis(protein_sequence)
    return analyzed_seq.molecular_weight()

# Example sequence
protein_sequence = "MKRISTTITTTITITTGNGAG"
print(get_molecular_weight(protein_sequence)/1000,"K Dalton")

# read fasta file path

file_path=SeqIO.parse(protein fasta file path)

# create function to calculate mw for all proteins
'''r
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
'''
    # calling function




