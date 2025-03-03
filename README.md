# rosalind_challenges
[![linkedin logo](https://rosalind.info/static/img/logo.png?v=1637535648)](https://rosalind.info/problems/list-view/)
### Rosalind é uma plataforma de aprendizado de bioinformática por meio de resolução de problemas.
- Aqui estão desafios que solucionei utilizando programação Python.

## #Contar nucleotídeos do DNA
- Dada uma sequência de DNA, retornar a contagem de "A", "C", "G", "T", respectivamente e separados por um espaço.
```
INPUT: "CATACACTCTGGATCTATACCGCCGTGTCTCATATCCACAGGAAGCTATGTACCTAGCAAAGGGTTGTCTTCAGATATAGTTGGCACTCGGAACTGGTTAAGCAGCAGACTTAACCCGCTGAGCCATGTGTCCTCCACGTCAACCAACTATGTCGAAGAACTAAGCGTGGAATAGCGATATTTTCCCCCGATCGCCTACGGACCGGGCCGAAACCGTTGCTCAACGGAGTTACTAAAACCAACGTTCTACACCTGAGCATCAACCGGCCGGGTGAGTTGCCAGTACACTCTGATAAGCGCGCGCCGTGGCGAACCCCTAAGGCCATGTTAGCTTCGCGCCTTTAGTAGAATGGAGCGGGGAAGCGGCACAAAAAGATAGTATTTCGTCTTATCGTCGCCTAGTTCGTAGAGATCACTACTAGTTGTAGGGACTGAAACGCTATGGTTGGCTGCGGATCCTCGAGGTAAAACCCTTGGGCTGATTAATGCCTATATTGTATACCCAATGAACGATAATCGTGGAGTGCACGAATTGAAACGATCTAATGATGGATGTGGAACCCAACGTGCATCTCCAAAACTAGATTTATTTACGCGCAGCGATCGGGGAAAGCGACCATTCTTCCAATTGGCCAACTCCTGGGCCGGGCTTCCACATCCCGTTGTGTAGATCAGGATAGGACTTATGCCCATCCCCGGGGTTGCATGGTCTCAGCCACATTTTCCCGAGTGGCTTGGTAAACGTTTAGTCAGCTTTTCCAGTTAAGTTAAGCACATCTTGCTCGACCCCACACCCATAACCGAATCACCCACCCTTAGGAGATTGTACCGCGATCGCTTCTAGACCCTAGCCCGCACGCACCGTTACTCCGGGCCCTTTTGCGTCGCTTTTCACCACTCTCACCTTTTCTCAAGTTTATAACGTGTTGCAGCAACGGCAATCCACGGATTTCTGCCCACATAGCCAGGGACATGACT"

```
- Pipeline desenvolvido:
```
#Entrada da sequência do usuário e criação do dicionário com os quatro nucleotídeos
sample = str(input("Digite a sequência de DNA para contagem de A, C, G, T"))
sequence = list(sample)
dict_count = {"A":0, "C":0, "G":0, "T":0}

#Iteração da sequência e contagem de cada nucleotídeo da sequência
for i in sequence:
  for k,v in dict_count.items():
    if i == k:
      dict_count[k] = v+1
      
#Resultado da contagem
print(" ".join(str(i) for i in dict_count.values()))
```
- Resultado ✅
```
OUTPUT: 242 270 226 240
```

## #Transcrever DNA em RNA
- Dada uma sequência de DNA, retornar a sequência de RNA, substituindo "T" por "U".

```
INPUT: TTTTATTGAAATCCTCTATTCTGACAAGTGCGCTCAAGAACTAGTTATATTGTTAAGACGCTGATTTCCTACCCGGACATTGAGGTCTAGCGAATCCCTGCTGCGCGCAAGAAAAAAGCAAGTTAACGGATTTACTGCTGGCCTGTCACTGTTACGTGTCCGTTACCCGTTTCATACAGTTTACGCGGGGAGGGATTGCATGGCAGTTCTTTGAAGCCTTGATGGCATAGTTACTACATGGGACGTAATGCACAGTCTTGGAGGTCCCCCACACACGGAATGATTCGTGCTATTATACTCCGACCAGGGTTACCTGCCGTACTGACATCTGGAGATTAAAATCGTATAGCTTCAAGATAAGCTACATCAACTTATCGAGAAGGCCGGTCGCTTCCCTGGACCTTGACTGCATTCCCCGTTTGATCCTTGAGTTAAACTGCAAAATAAGGTGTCCGTCCTTAGGTTCTTGCCCGCACTGTCGATTTGCGGGGGTGTTTTTAGGGATTCAGAAAGCAACGGCGTGTTCTATCAAAATTCCTACTATGCAATCGCCACCTCGGCCTGTCGCAAACCGGAAATTAGCGTTTTACTTTATGGTTACTGAGCTATGAACAGCTGACTTTTGATGGCTGAGGGGAACAGAAAGCCCCTGATCGCCCCGGATCCCCTAATTAGTTGGGAATCATGGAGACGTACGTCGCAGGCGCGAGAGAGGTGGATCTCATGTCCGCAAGAAATGAATGGTTGCATCCGAATACGGTCGTGTCTAAGGGCTTTACCATCCGCGTTTGGTGAGCTCTAGTGGACTTGGGGGAAAGATAACGAGATACACTACTAATGAGTCGCCATGGCGCTGCCGTTGCGCCTTTCAAAAGCCCGCGGACGTTCGGATCGTGTCACCTTGTATTCGGAATTCCGACTACACATAGTTGCCCTTAATACGTCTTTTCTCAATCGTATTTTTCAGCTAACAGACCGTGTGCTGG
```

- Pipeline desenvolvido:
```
#Entrada da sequência de DNA pelo usuário
sample = str(input("Digite a sequência de DNA para transcrever em RNA"))
#Substituição de T por U (transcrição)
result = sample.replace("T","U")
#Retorno do resultado (sequência de RNA)
print(result)

```
- Resultado ✅
```
OUTPUT:
UUUUAUUGAAAUCCUCUAUUCUGACAAGUGCGCUCAAGAACUAGUUAUAUUGUUAAGACGCUGAUUUCCUACCCGGACAUUGAGGUCUAGCGAAUCCCUGCUGCGCGCAAGAAAAAAGCAAGUUAACGGAUUUACUGCUGGCCUGUCACUGUUACGUGUCCGUUACCCGUUUCAUACAGUUUACGCGGGGAGGGAUUGCAUGGCAGUUCUUUGAAGCCUUGAUGGCAUAGUUACUACAUGGGACGUAAUGCACAGUCUUGGAGGUCCCCCACACACGGAAUGAUUCGUGCUAUUAUACUCCGACCAGGGUUACCUGCCGUACUGACAUCUGGAGAUUAAAAUCGUAUAGCUUCAAGAUAAGCUACAUCAACUUAUCGAGAAGGCCGGUCGCUUCCCUGGACCUUGACUGCAUUCCCCGUUUGAUCCUUGAGUUAAACUGCAAAAUAAGGUGUCCGUCCUUAGGUUCUUGCCCGCACUGUCGAUUUGCGGGGGUGUUUUUAGGGAUUCAGAAAGCAACGGCGUGUUCUAUCAAAAUUCCUACUAUGCAAUCGCCACCUCGGCCUGUCGCAAACCGGAAAUUAGCGUUUUACUUUAUGGUUACUGAGCUAUGAACAGCUGACUUUUGAUGGCUGAGGGGAACAGAAAGCCCCUGAUCGCCCCGGAUCCCCUAAUUAGUUGGGAAUCAUGGAGACGUACGUCGCAGGCGCGAGAGAGGUGGAUCUCAUGUCCGCAAGAAAUGAAUGGUUGCAUCCGAAUACGGUCGUGUCUAAGGGCUUUACCAUCCGCGUUUGGUGAGCUCUAGUGGACUUGGGGGAAAGAUAACGAGAUACACUACUAAUGAGUCGCCAUGGCGCUGCCGUUGCGCCUUUCAAAAGCCCGCGGACGUUCGGAUCGUGUCACCUUGUAUUCGGAAUUCCGACUACACAUAGUUGCCCUUAAUACGUCUUUUCUCAAUCGUAUUUUUCAGCUAACAGACCGUGUGCUGG
```
## #Retornar a sequência reversa complementar de DNA

- Dada uma sequência de DNA, retornar sua sequência reversa e complementar. (p. ex. o reverso complementar de "GTCA" é "TGAC")

```
INPUT:
ATTCTACACCTCTGAGCTGCCCGTACGAACATGGGCTACGTCACTGCTCAAACTCAAGTCAGATCGTGCGCGCGAGCCTTAGATAACTAACGAGTCAGCCAATGGATTCCGCGTCAATGGATTCGGGCATCAGCTTTGGCCGGGGCCGCATTTATCAATCCGACTGACTTCCCGCAATACTTCCACGCCTCGGGCTATTGGGAAAATTAAGGCAAGTAACGCGTTAGTCGCTCGCGAACTCCTATAAAATTATACTGGAGCCGGTGTGCTCTATGCAACATTATAAGTGAACTTCCTGTCTATGTGGGGTGAAATGACGCAACCCAGGCCTCATCACAGCGAAGTCTAGCCGGAGTGATTTGGCATAAGCGCGCTTGGGGTCCGCACGGTGGGCGGATGCTTCACAGATAACATATAACAGTAATAAGTACTCCGCGTCGAATTCGATACGGGGCTTGTATACAGGGCTAGGTTAGCATAGGCACTGAAGCGTGAAAAACTGATTTCGCCGTGAACCATATCAGACCTTGGCGTCAAGAGGAGGTTGCGGCTTGCCAATACATTAAGCTTGACCTCACACCGGTTTCGCGTCAGATAATTGGTCATTTTACTTTGCGAAAACGTAAGAGCCGGTTCTCTTCAGCGGGTCTGGTCTGTGTTAGGCGAAACGAGTAGAGAGAGGAAGAGTTACCTTGTATCTGAAACGCGCGACTCGTGGCCCACATCTGGACACCGCCGTCAAACGCGCGGACTGAGTGACGAGACACGGTAATAGTACGCTAATAGGACCGGTTCAAGGACCTGGCCACCGGTAGTCGGTTCCACATTCGACGCAGGTACATCGTGATTGTGGGTATCCCACCAACTGCCTCTAATCTTTTGCTTCTAAGCGAATATGAGA
```
- Pipeline desenvolvido:
```
#Entrada da sequência de DNA pelo usuário
sample = str(input("Digite a sequência de DNA para retornar o reverso complementar"))
#Revertendo a sequência dada
reverse = sample[::-1]

#Criando dicionário com base referência:base complementar
dict_compl = {"A":"T", "G":"C", "C":"G", "T":"A"}
#Criando string para armazenar sequência complementar
complement = ""

#Iterando sobre a sequência dada, e armazenando a base complementar na var "complement"
for i in reverse:
  for k,v in dict_compl.items():
    if i == k:
      complement += v
print(complement)
```
- Resultado ✅
```
OUTPUT:
TCTCATATTCGCTTAGAAGCAAAAGATTAGAGGCAGTTGGTGGGATACCCACAATCACGATGTACCTGCGTCGAATGTGGAACCGACTACCGGTGGCCAGGTCCTTGAACCGGTCCTATTAGCGTACTATTACCGTGTCTCGTCACTCAGTCCGCGCGTTTGACGGCGGTGTCCAGATGTGGGCCACGAGTCGCGCGTTTCAGATACAAGGTAACTCTTCCTCTCTCTACTCGTTTCGCCTAACACAGACCAGACCCGCTGAAGAGAACCGGCTCTTACGTTTTCGCAAAGTAAAATGACCAATTATCTGACGCGAAACCGGTGTGAGGTCAAGCTTAATGTATTGGCAAGCCGCAACCTCCTCTTGACGCCAAGGTCTGATATGGTTCACGGCGAAATCAGTTTTTCACGCTTCAGTGCCTATGCTAACCTAGCCCTGTATACAAGCCCCGTATCGAATTCGACGCGGAGTACTTATTACTGTTATATGTTATCTGTGAAGCATCCGCCCACCGTGCGGACCCCAAGCGCGCTTATGCCAAATCACTCCGGCTAGACTTCGCTGTGATGAGGCCTGGGTTGCGTCATTTCACCCCACATAGACAGGAAGTTCACTTATAATGTTGCATAGAGCACACCGGCTCCAGTATAATTTTATAGGAGTTCGCGAGCGACTAACGCGTTACTTGCCTTAATTTTCCCAATAGCCCGAGGCGTGGAAGTATTGCGGGAAGTCAGTCGGATTGATAAATGCGGCCCCGGCCAAAGCTGATGCCCGAATCCATTGACGCGGAATCCATTGGCTGACTCGTTAGTTATCTAAGGCTCGCGCGCACGATCTGACTTGAGTTTGAGCAGTGACGTAGCCCATGTTCGTACGGGCAGCTCAGAGGTGTAGAAT
```
## #Traduzir mRNA em proteína
- Dada uma sequencia de mRNA, retornar a sequência de aminoácidos codificados (primeira letra correspondente ao nome do aminoácido)
```
INPUT:
AUGGGAUCGCCGAGUUAUUGGGGAGUAACGUCGAGGACUCGCACUACAUGGCCAAUACCGCCAAUGUGUCUCUCAUCCACGACGGGAACGGUCAAAGGAGUUUUCUUCAGGCUUCAGGACCCUGCUUGGUCAAGCUGCAGACGUGACUGCAAUCCGGCAUCGCUCCGCGCGGCGCCUAUAGAUCAAGAACGUAUACGAAUGGGGGAUAGAACUGAGACACCUUGCCAUAGAUAUUUCUACAUACUAUUAUGCGUAGACCGUAGAAAGGGUCUGGAUGUGGUCAGUCCGAUUCGUAAGGUCAGCUGUGCUUUGUCAGUAUUAAGGGCACACCCCCUUAAAACGUGCAGUUCAGGACGUGCAGCGCGGAGCGCGGCUACAGAAAUAAAAAGCGGAGCAUCGCGUGACACAAAUCCGCGUGAGCACGUGGGCUUACGACUGUGCUCCGUCGGGUCUAAAAUACUUUGUCGCGGAGUUGAACGAAAUUCGGCUAGAAGCAUGUCAGACGGCCUAAAUAUAAAGCUUGUAUUUCAUGAAAGGAAAUCAGACGCCCAUCCUCCAUGGAUCCGAAAAAACGCGGCGAGGUCUCGCCCCAUGUGGUUAAUUUGCUGGUGGACUCUUUCUCAAGUAGCCCGCCCCAAACUACGACUUCACCCUGAGCUCUUGUGCAACGGGAAUCCGCAGAGGGCGUAUUCAAUAUGCAUGGGCACACUGGGUCCAAGAAGCCGUCGGAGGACCAGGGUACCGGGUACUGGAAUCUCAAAGGUCUUUUUCUGUUUGAGUCUACCUACCAUCGAACGAAAACAGGGUUGGCAGAUCCAGACGGCCGACUUCGUUGGAAUUCAACACCGUUCUGCCGAUGAUUACCCCCAACCCCAUGGCAUUGGACCAUUGAACCUAUCCCCUUACGGUCUGCUUACCAGUCGGCACUCACGUUCCUCGCUCCAUUCGACCGGGGUAUACGUCAUGCAAAGACUGUGCGUUUUUAGCACCUUGGAAUAUAGGAUUGGAAAGCCGUCUUUGAUGGGCCUCCCAAAGUUGAGUAACCGUCCGCGGCUAGCCGCAUGCGGGACAUUGGAUCGACCGACAUUCGGAACAGUUCCUUUCGAUAUUAUACGUAGUCGCUCGUACUUAGUUAUGGCGUGCAGGCAUAAUUUCUCGCCGGGCAGUUAUCCUAAUAUCAUAGAUCCAAGGGUGUCACUGUCGAUACCGGCCCUAGCCUCGGGUAAUUAUGAGUGUCAUUUCGGACCCAUCAUCCCCCGAGGCCCUUGCGCAGGGUUCCGCGUUAGUAUCGUAAGAAACUUAUCAACGAAAAUUUUUUGGCGUAAUCCAAGAGUUGAUUACGUAACUAACUAUUUAGAGAGAGAAGCGCCCGCCUACUGUGUAUCAAAUGGGAGCCUGUGCAGAGUUCACCAUUCCUACAAGUGCGGGAGGAUUACGCACAUGCCCGCGCCCCCGACUAUUAACCUUACAAGGGCUUCGAACCCUGCUGGGGUAAUUUUUAUUCUCGGACAUGCAAGAGUUCCUUUGUUAUUCGGGCCCUCUACCAAUUCGCAAUCCCUGGGAAUGCUUCACCUCACAAUCGAUAACACGGACUUAAAAUGUUACGAACUUGGUCUUUAUCCACCUCUAUCACUGUAUAAAUUUGAUGGGAUAUCGACUCGAUGUCGAUGUAUCUCAGUACCCACCUUAGUAGUCAGUCCUAAUAUCUGUGCUACGCCUCGGUAUGUAGAGUACGUCUGGCACCCACGUCGGCCCGAUCUGCGUCUUCAACACGCUCUCCUUACUUCCAACGGCCCCUCCAAGUUCACGACGGCCUUCAAGUUUGGCCGAGGGAGUCAAGCUCCCCCAGCCAAUCCUGUUACUCAUCGCGUGUAUCUCAGUAGUACCCCCGCUAAAGCCACGGGGCGUUCGACGGAUACCCACGAGGGUCUACAACGAGUUCAUAUGCGAGACUCUGCUACCCCGGUGGAUGUGACACUUCAGAGACGGCUAGCGUCUGUGAAUAGGGACGAAAUUUUCUGCGAAGACGAGAGCGUACAAAUGCCGGUAAUCCACGCAAAACUAGCUUCAGACAGAGCGGGUCGGUGCUACCCUCAUGAGAGGGUUUCGCCGCGGCGAACCUGUAAGCAGGAAAAUACGGUGCGAGACUUACAGCCCCCUGGUGAGGACUUAAAGUGGGCACGUCGAGAGUGGGAAAUGCAGACCCACCUUUCUACGGGCCACGCCCCAUGCGAUUCGUCACCCCUUUGGCAAACUAUGGGGCGCUUAGUCGAUAGAGUUGCUAAAGUCCUUAAGGGGACGCCUGCUCAUUCCAAAAGCAUUGCCAACUUCAGGCAGCAGGGAGGCCGAUUCGCUGCUCAUCCUUCAUUCCAUUGUGGUUCAGUGGGCCCUGCGCGGACGUUUGAGAAUUCCGCGUCUCCAAUAGACCGCUUAAUCCCCCACCAUAAAGAGAUACCCAGAACGCGACGUACGCUUAACAAAGGACGAACCGUGGCGUUAAGGGCGAAGGCAAAGGUUUUUUGUCAACCUGUUAAGCCCGAUUCCAGAAGAGGUCGUUACCGGUUUCUAAGUAAUACUGAGAUUCUUCGUUUUGUGCGGGCCAACGAUCCAUCAGUAUAUGUCAACUCAACUGGAUGCUGGAGGCCGACACGUUAUACGCCGUAUGAGCUAGCUAACCUCUCCACUAUUCUAGUCACCCUUCGAUAUGAACUUGCAACAUCAAUGCUAGAGGGUGUAAGUAGUGAGGCUAUUUCUCAUGUACGAGCACCGUCACCACUAUUGCAGAUGAGGGGUCGUCGUAAUUCACAAGUGGCGGAAACUGAUGUUCUCGAACGUGAGCCUGCCUCACCUAUGUUCCCGUCGGUACCCAGCCGCAACGGUUCCGAUUUAACUAGGCAGAACUUGUAUCUGUCAGGUCGGAGAACGAAGAUCCCGCGCCAGGCUUUACACUCAACUCCAAGUAAUAAGCACUCGAGUUCAAAAUGGAUCAUUAGAAUCGCCCAAGGAACUCGCCUGAACGCGCAGGCUCCAGUGUUUAUGGUGAACCCCUCUAGGUCGCCUUCAAUGCUAAACAGCGCGUUGCACGCCAGGGUGCAUCGCACGCCACUCCCUAUACUCAUCGAAACGGAUUCGUUAGCACACGACACUGUCUUCAUGAAGGAAACUUUCCGUCUACCAGUCGCGUCCGUAGAAACGAAUGGGGUGUCCGGAAAGCGGUUUUCAUACGGCCCUGCUUUAAGUCCCCGCGGCGGGUUUCGUACUAAAGUUGCAAGGGUAACUAGACAGUGCAGUCUACAAGCAACACGGAAGUGCAUCGCACGAAAGUGGCCGAAUGGUGUUUGGCUGCGAUUCCCUUGGCAGUUCCGACGGGUGCCGGGCGGUAUGCCGCUCGUGAAUUGGCAUGCUUGUGGGACACUUCGACAGCCUAAUGUUAAGAGCAACCCAGUGUCGCGGAUGUCAUACGCUCGAGUUUUCUGCGAGAGCGUUAUUGCCAGGCCCGGUGAAGGUUGGAUUCAUGGUAUUUGUACGCACGUCCCUCUAGGUGAACAUUACCGCCACCUAAUAUCGCCUGACGGUCGCAAGAUAAAGGACCUCAGAGUCGAUAGCGAAAUAGUCGCUGGGUCGACGAGGUACACGACACGAAUUCAUGCUCUGAUUCGAGAACAAUCAAACCGCACUGUAUAUCUUACAAGCCCCAACGUCACCAAUUGCGUCGUCGCACUUCCGAAUGUUCCGAUAGUUGCCCGACCGGUGCGAAGUCUAGCCAAUAUCACGCUGCGGCAGAGGCGGGAAGUCAGGUAUCUCCCGAAGUUAGGCAGGAGGCUUCCAUACAACCAACCAGCCUCAAUUCAUGUUGUCCUACAUAGCAGGCAAGGCCACUGGCUGGGUAGCAUGCGUAUGUACGUUAGUGGGCGCGGACCCGCGGUUCCCCUAGAGCAUCACUGCCCUCGGCUUUGGAUCCUGCAUCGCAUAAGAGAGUAUGGCCGAUUUCGCGGCUCGCCAGAUCUUAAAAGUAUCUCACCGCAUAAGCUGGGGAUAAACUCCGUUCUAAGGUCAUCGAAUGAUGAAGUAAGCCUGAUUCACCAGAACCCGCGUUUAUACCCGAGUAUACUAAACACAGUGCAUACGAAUAUAACUCGUGGCGGCCCGACGGGUGCGCCGGGUCGGGGUCGUCUAAGUUCUUGCACCACGCGGGACCCAGCUUCGUCCGGGUGUGUCAUGUUUAAAACCACACAAACGAGCAAGGACCAAGAUUUGCUGUUCUAUGAGCCCUCGGAACUAUCGGGUAAGAUUAAUUAUGAGCUCGCGAGAAAAGCUAGUAAGCGUUGUCAGGCACGGGGAUUGAGUCGAUUACCCGACCCGCCUUUUAACCGGCUUUCAAAAUGUAAUGAAAAUUACCACGCCAUGUUCCACGGAUUUCUUGCAGAGCAGAACGAUGCGCAGUUAUCAGUGCUAAGGACUAGUCAGAGAGCUAACGAAACUAACGUCCAUAGACAUGACCGGGCGAUUCAGUCACGCUGGCGAGUAAUGCUCCCACGGUUACGCGGAGGGUGGCGGCCUCGGAAUAAUGACCCCAGGGGAGGUAUUUAUCGCCAGACAAGUUCUUUGGCUAUUGAAAACUUGUCCAUUUACCGCUAUAGAUGCUCAGCGAUAACCGGGCAAACUAGAUGUAUAUUGGCAGUCAGGUCCCCGUGUAUACGGGUGGGAUCUAAUAUCCCAUUAACUCUGUACACGGAUCUUGACGCCCCGGAGGAUCGGUUGAGCGUUGCAGAUUUGUGCCACUAUUGGUGCGCCACUAUACGCAGGUAUUACGAUAGCCUGGCUGCGGGCAGAGCAAUGUUUAAUGGACGAGCACUUCGAGAAUUACAGUCGGGGAAACUAUUUGUCAUGUUUACACACAGGGUCAAUCCUGCAACGACCAUCUACACUCAAAAGGCAGCCUCGGUCUUCUUUCGCAUACUAUCACCCACUGACUCCCCAGUGACACGGAACGAUCUGCAUUGCGCAAUCCGGUCCCGGCCCGGCAACUUAAAUGUCAACCUAGAUACGCCCAUGAAACUCUUAGAAAAGGGCCGCAUCGGCUGGCUGGGUGUUGGUAGGUUUUCCACGUACAAGGGCCAGGAGCAGCAACAUGGAGGAGCGGGGAAGAACGUUGUUUCGCUCCAAAGGAUACAAGGUUGUUACUCCAAGGGUAGUAUCCACGCAACUGAGCCUGUUUUGUUGUUCUCUAUGUUAAAUGACCUUUCCGUCAGAGCGGACUUCAGGUUCCACUUAGUACUCACCUGGCUAAUCGUCUGUCUUGCGUUCCGAGUGGGAGCGGUGCGGCGACUUCCAAAUGUAGUUCGGGUCCGAAACCUCGAAAUUGUUACUUUUCGGGAGUUCCCCUAUCUCGGUAACACGCAUACGGAACAUUGCUGGACCAUCCUGAUGGCACGGGCGAUACUGGCGAAGCCCCAGAUGUGUCAAAACAUACGGAACUUGAGUAAAAAUUUAUUCAGAGCCCUAGUACGAAUAGUCAGUUCGGGCAUCCGUGCUCUUGUGGAAGGAUGUGACAUUGAUCCGAUUGAAUUAGUACCAGCACGGCGUAUCUACCCCUUGGCCCUAAAUCUGCGCGGGAGAUCUAACACUAGGAACAGUCCUCAUCACGGACUGUAUUUAUUGCACCUUUGGCGUGGGUCUUCGACGAGUGUAAGGGUAGCGGGGUACCUGUUCAGUCUUACAUAUUACGCUACGUGGAUACUCAGUUUAGAUCGCAUCAUAGUCAAGAUUGAAUGGUACGUGCAAUCGAUGGUACUACUAUAUAGGGGCACUUUACCUACGGGGGUCGACCAGGGGUCAGACCCCGCCAUCGAACAUUGGGAGUUCACUGUCGUCAGCAAGAUCCCCUAUCGUGUAGUAACUAGCGGUCCGUCCGCCUGGCGGGUAUCUCAUAUACAAGUCCAGUACCUCUCAAAUCCUCAAGCAGCUCGUUGCGAGAACAUGGUACCAUUAGGGCACAAGUCGAGGUCCUCCUCCUCAGAACUGUUAAGCCUCACCGUUUGCUGCGCAUUUUCCCUCCGGGGUUCCGCGCCACAUAGCAAGGACAGUCUUUUGCUGAGACACAUAGUCCUACUAUUUUUCAAACUAGGGCAUCACACACGAAGGUAUAACAGUAACCUCCGCGGUUUAACGGUUUUUAAAAGUCAAACCAGUGGUUGGAUAAAUGUAUCAAGUGCAAUACCACUUUUUGAGGUAACUCACUUAACUGACCAUCAGCCUCGACUUUUUUUCACGGUAAUGUCUGCUCAAUCUGCAAACACCAUUUCACCUCAAAUGAUUCCUACAGCUCCUAAGCACCGUCCGACCGGACGUUACAUGGAGUGGGUGGCGAUCCCCAUUACGGACACUGGACGUCCGAGGGGGGACGCUAGUGAGGUUAGAAUGAGCAUGCGCUCCCCUAAUUACACCUCGCUGACGCUGCACCCAUUCCGUGCCCAUAACGUCACUUUUUCAAAGGGCGGCGGUACGAAGGUCCAGUAUAUACCCAGCGACUCUGGCCAAUGGUUCUAUAUACAGCGCGGAUUUCGUCCGACAUUAAGCUGCACAGAGCUCUCUCAUCCGCAGCAAAACCCGCGCACGAGUUGCCUCGCUUUAGAAAAACAUAAAAAAACGUGGGCUCCCGUGUCUCUUAGACUAGCGGAAAAGGGAGGGUACCAGGGAAACUUGGGCGUACCGGAUCCGCGUAUGCGUGUUUCUGGGAUCGGCAAAUCUAUGCGUGAAGCCGUUGAGGCACUGAUCGUACGCUGGUGUGCCGAUGACUUGAGCAGGGGAAGUCCGCGUUCAACAGGUGGGGGGCCAUCGUGUGCUGUUAAAAAGUUUUAUAUCUGGACGGUUCAAUCGCAUAAGGCGCGUGCGGGUAGCGGUAGCACCUGGACACAUCAGUGGGCUCCCAUAGCAAGCUCGAACGCACUACGAUGUAAAACGACCGUAAACCUUGCGGCCCAACAUCAUGAGUUGCCAACUUCUAGCCAUCCCUCGGGAGAACCCAUCUACCCUAUUAUACGUUGUCGCUUUAAAGGGUCACGCCGAGGGGUCGCGGUGGACGAUAAAUGGCACCUAGUUGCCCUAGUCCGCGAAGAAGCACAUCGAAUUCUCGAGAUUCGGUCAGUAGGUCCACACUACCAAAUCUCCGCUUGGUUAACAAAAAUGUCUACCUUUUAUACACUGAUCGAACUUGCGAUUACCCUAACUCAAUUUCAACAGCGUGUGAGCAUGAAGAUAUUCGACGCUCGACGCGUAUUAGUGGGCCAGAAGCAUAGGAGGAAAUAUAGCACAAGCUGCCGUCCCAGUUUUGCGUGUACCUUGGGGCGAAGAGAGGUGACUCUAGAGCGUUGGACUCGUUGCUUAAUCGAGCUUAUUGGUGCCACCCAUGGAUCCUACGUGUGCAGCUCGCUUCAAUAUUUGACUAUCAAUCGCGGUGUAAUGACAGACAGGCCUGUGUGCGUUCACUUUCACAGUAUUUUUUUUAGCUAUCGGAACACGGUGCACCUGAUUGGGGCCUCGAUAGGCUGGUGUACCGUCGCCGUUGAGAAGACACGGACAGACGGCUUACGGCUUUAUAUAUCUGAUUUACAUGAGGACGUAGCAUAUAUGGAAAGAGUCGUUAUAUGUUGUAGGUCGACAGAUAGAAUCAUAUCGCAUCAGAUAGGCACUCAGCCCCCCAUGAUCAAGAACCGGAUGUUAAGCAUAGGGGAGAGUGGGGUAGCUGUACGUCGAGUGUCAGGUUUCCUGAGCAACCGGCUGUGGGCGUACGCGUUCCUGUCGUUGUUCGUGAGGAACGGGCUACGACGUCAACUCAAAGCAAGAUACUGGGCUAAGUUUCGGGAGCGAGGGCAUGGAGUUACCAACUUGUUAGCACGCCCGAGCUACAAAUCCAUCGUAGCUCAUCUCACUGUCGACACAAAUUAUGUCUCGGCGGUACCAUUCCGUGCGGACGGAGGCAACAGGACUCCUGGACGGAGUCUUUGCUGUAUCAGUUGCAUGAUGAAUUUCUGGAAACUUAACUGUCGCCAAGUAUGGGAUAUGGGCAUGGACCGCCACGUUGCGAUUAGCAUGAUCUGUGUAAGUGCAGCAGCCUUGUCAUUUAUCUGUUCUGCUGAAUUACCGCCAAGUGGCUUGAAAGGGAGAACCAGGGGAUGUGACCGUCGGACUAUAUGGCCAGUGGGCGGCCCCAGGUCCCCUAGGUUGUCCAUUUCUGACAGCAAGGGCAUGGACACAGUCAGUCGGACCCUAGGACGCCCGAUUCUGCGUUCGGGGAGAAGUGAGUGCCUACAACAUCUUCUGAAUUCAAACAGGAUCAAACAAGCAGAUGUAGGGCAAGUAGGCAGGGCGCGCUCGCUCCAUAAAAGGAAGACAUGUAUGAUUAAUAAGUGGGGAGUACCGUUUGGACAUCGUGCGAAAGUAUCGCGAGUAAGUAAUACCAUUGGGCCAGUGUGGAAAAGCGUGAUUCGCUUCACGGGAGUUAAAAGUCACUUAGACACGAAAAAUUGCGCGGGGUACCUAGCGCUGCAAGCCCAUUACAUGCGAAGCACAUAUAACAGCGACGUCUACAACGUAUUUCCGUACGCGGUCCUAUACAUCGCGGUGCGUAGUGACGUACUGAGCCGUCAGCACACACAAAAUCUCGUAUUAACGCCGUUUUAUUGCUUCUGGAUAUUGUCGACUAUUAUGGCAUUUUCGGCGCGGCGAGCUGGUAGCCUCGUCUGCCAUAGCCGUGGGGCCCGUAACAGAACCGUCCUUGAGCCCUCCCUACUGCGACUCCUAUAAx
```

- Pipeline desenvolvido:
```
#Entrada da sequência de RNA pelo usuário
sample = str(input("Digite a sequência de mRNA para retornar a sequência de aminoácidos"))

#Dicionário contendo codificação das trincas mRNA(chaves), nos 20 alfa-aminoácidos (valores)
dict_prot = {"UUU":"F","CUU":"L","AUU":"I","GUU":"V","UUC":"F","CUC":"L","AUC":"I","GUC":"V","UUA":"L","CUA":"L","AUA":"I","GUA":"V","UUG":"L","CUG":"L","AUG":"M","GUG":"V","UCU":"S","CCU":"P","ACU":"T","GCU":"A","UCC":"S","CCC":"P","ACC":"T","GCC":"A","UCA":"S","CCA":"P","ACA":"T","GCA":"A","UCG":"S","CCG":"P","ACG":"T","GCG":"A","UAU":"Y","CAU":"H","AAU":"N","GAU":"D","UAC":"Y","CAC":"H","AAC":"N","GAC":"D","UAA":"","CAA":"Q","AAA":"K","GAA":"E","UAG":"","CAG":"Q","AAG":"K","GAG":"E","UGU":"C","CGU":"R","AGU":"S","GGU":"G","UGC":"C","CGC":"R","AGC":"S","GGC":"G","UGA":"","CGA":"R","AGA":"R","GGA":"G","UGG":"W","CGG":"R","AGG":"R","GGG":"G"}

#Lista vazia para armazenar os códons
sample_codons = []

#Iteração que separa a cada 3 bases o mRNA, criando os códons
for i in range(0,len(sample),3):
  sample_codons.append("".join(sample[i:i+3]))
print(sample_codons)

#String vazia para armazenar inicial dos aminoácidos  após tradução
amino = ""

#Iteração das chaves do dicionário, dos códons e armazenamento dos valores correspondentes (inicial dos aminoácidos)
for i in sample_codons:
  for k,v in dict_prot.items():
    if i == k:
      amino = amino+v

#resultado da tradução
print(amino)
```
- Resultado ✅
```
- OUTPUT:

MGSPSYWGVTSRTRTTWPIPPMCLSSTTGTVKGVFFRLQDPAWSSCRRDCNPASLRAAPIDQERIRMGDRTETPCHRYFYILLCVDRRKGLDVVSPIRKVSCALSVLRAHPLKTCSSGRAARSAATEIKSGASRDTNPREHVGLRLCSVGSKILCRGVERNSARSMSDGLNIKLVFHERKSDAHPPWIRKNAARSRPMWLICWWTLSQVARPKLRLHPELLCNGNPQRAYSICMGTLGPRSRRRTRVPGTGISKVFFCLSLPTIERKQGWQIQTADFVGIQHRSADDYPQPHGIGPLNLSPYGLLTSRHSRSSLHSTGVYVMQRLCVFSTLEYRIGKPSLMGLPKLSNRPRLAACGTLDRPTFGTVPFDIIRSRSYLVMACRHNFSPGSYPNIIDPRVSLSIPALASGNYECHFGPIIPRGPCAGFRVSIVRNLSTKIFWRNPRVDYVTNYLEREAPAYCVSNGSLCRVHHSYKCGRITHMPAPPTINLTRASNPAGVIFILGHARVPLLFGPSTNSQSLGMLHLTIDNTDLKCYELGLYPPLSLYKFDGISTRCRCISVPTLVVSPNICATPRYVEYVWHPRRPDLRLQHALLTSNGPSKFTTAFKFGRGSQAPPANPVTHRVYLSSTPAKATGRSTDTHEGLQRVHMRDSATPVDVTLQRRLASVNRDEIFCEDESVQMPVIHAKLASDRAGRCYPHERVSPRRTCKQENTVRDLQPPGEDLKWARREWEMQTHLSTGHAPCDSSPLWQTMGRLVDRVAKVLKGTPAHSKSIANFRQQGGRFAAHPSFHCGSVGPARTFENSASPIDRLIPHHKEIPRTRRTLNKGRTVALRAKAKVFCQPVKPDSRRGRYRFLSNTEILRFVRANDPSVYVNSTGCWRPTRYTPYELANLSTILVTLRYELATSMLEGVSSEAISHVRAPSPLLQMRGRRNSQVAETDVLEREPASPMFPSVPSRNGSDLTRQNLYLSGRRTKIPRQALHSTPSNKHSSSKWIIRIAQGTRLNAQAPVFMVNPSRSPSMLNSALHARVHRTPLPILIETDSLAHDTVFMKETFRLPVASVETNGVSGKRFSYGPALSPRGGFRTKVARVTRQCSLQATRKCIARKWPNGVWLRFPWQFRRVPGGMPLVNWHACGTLRQPNVKSNPVSRMSYARVFCESVIARPGEGWIHGICTHVPLGEHYRHLISPDGRKIKDLRVDSEIVAGSTRYTTRIHALIREQSNRTVYLTSPNVTNCVVALPNVPIVARPVRSLANITLRQRREVRYLPKLGRRLPYNQPASIHVVLHSRQGHWLGSMRMYVSGRGPAVPLEHHCPRLWILHRIREYGRFRGSPDLKSISPHKLGINSVLRSSNDEVSLIHQNPRLYPSILNTVHTNITRGGPTGAPGRGRLSSCTTRDPASSGCVMFKTTQTSKDQDLLFYEPSELSGKINYELARKASKRCQARGLSRLPDPPFNRLSKCNENYHAMFHGFLAEQNDAQLSVLRTSQRANETNVHRHDRAIQSRWRVMLPRLRGGWRPRNNDPRGGIYRQTSSLAIENLSIYRYRCSAITGQTRCILAVRSPCIRVGSNIPLTLYTDLDAPEDRLSVADLCHYWCATIRRYYDSLAAGRAMFNGRALRELQSGKLFVMFTHRVNPATTIYTQKAASVFFRILSPTDSPVTRNDLHCAIRSRPGNLNVNLDTPMKLLEKGRIGWLGVGRFSTYKGQEQQHGGAGKNVVSLQRIQGCYSKGSIHATEPVLLFSMLNDLSVRADFRFHLVLTWLIVCLAFRVGAVRRLPNVVRVRNLEIVTFREFPYLGNTHTEHCWTILMARAILAKPQMCQNIRNLSKNLFRALVRIVSSGIRALVEGCDIDPIELVPARRIYPLALNLRGRSNTRNSPHHGLYLLHLWRGSSTSVRVAGYLFSLTYYATWILSLDRIIVKIEWYVQSMVLLYRGTLPTGVDQGSDPAIEHWEFTVVSKIPYRVVTSGPSAWRVSHIQVQYLSNPQAARCENMVPLGHKSRSSSSELLSLTVCCAFSLRGSAPHSKDSLLLRHIVLLFFKLGHHTRRYNSNLRGLTVFKSQTSGWINVSSAIPLFEVTHLTDHQPRLFFTVMSAQSANTISPQMIPTAPKHRPTGRYMEWVAIPITDTGRPRGDASEVRMSMRSPNYTSLTLHPFRAHNVTFSKGGGTKVQYIPSDSGQWFYIQRGFRPTLSCTELSHPQQNPRTSCLALEKHKKTWAPVSLRLAEKGGYQGNLGVPDPRMRVSGIGKSMREAVEALIVRWCADDLSRGSPRSTGGGPSCAVKKFYIWTVQSHKARAGSGSTWTHQWAPIASSNALRCKTTVNLAAQHHELPTSSHPSGEPIYPIIRCRFKGSRRGVAVDDKWHLVALVREEAHRILEIRSVGPHYQISAWLTKMSTFYTLIELAITLTQFQQRVSMKIFDARRVLVGQKHRRKYSTSCRPSFACTLGRREVTLERWTRCLIELIGATHGSYVCSSLQYLTINRGVMTDRPVCVHFHSIFFSYRNTVHLIGASIGWCTVAVEKTRTDGLRLYISDLHEDVAYMERVVICCRSTDRIISHQIGTQPPMIKNRMLSIGESGVAVRRVSGFLSNRLWAYAFLSLFVRNGLRRQLKARYWAKFRERGHGVTNLLARPSYKSIVAHLTVDTNYVSAVPFRADGGNRTPGRSLCCISCMMNFWKLNCRQVWDMGMDRHVAISMICVSAAALSFICSAELPPSGLKGRTRGCDRRTIWPVGGPRSPRLSISDSKGMDTVSRTLGRPILRSGRSECLQHLLNSNRIKQADVGQVGRARSLHKRKTCMINKWGVPFGHRAKVSRVSNTIGPVWKSVIRFTGVKSHLDTKNCAGYLALQAHYMRSTYNSDVYNVFPYAVLYIAVRSDVLSRQHTQNLVLTPFYCFWILSTIMAFSARRAGSLVCHSRGARNRTVLEPSLLRLL
```
