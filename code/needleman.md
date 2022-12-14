---
layout: markdown
permalink: /code/needleman
title: "Needleman-Wunch"
author: "Liang Liu"
output: html_document
date: 2021-04-16
---

The Needleman-Wunch algorithm is a dynamic programming for pairwise alignment. Given the score function and two sequences, this algorithm can find the global best alignment. 

#### Define a score function and two input sequences for alignment
```{r}
score=c(1,-1,0)
seq1="AGTC"
seq2="ACGTC"
```

#### Create matrix M
```{r}
ncol = nchar(seq1)+1
nrow = nchar(seq2)+1
M = matrix(0, ncol = ncol, nrow = nrow)
colnames(M) = c("",unlist(strsplit(seq1,split="")))
rownames(M) = c("",unlist(strsplit(seq2,split="")))

coln = c("",unlist(strsplit(seq1,split="")))
rown = c("",unlist(strsplit(seq2,split="")))

move = M
```

#### Initialize matrix M
```{r}
for(i in 2:ncol) M[1,i] = M[1,i-1] + score[3]
for(i in 2:nrow) M[i,1] = M[i-1,1] + score[3]
for(i in 2:ncol) move[1,i] = 1
for(i in 2:nrow) move[i,1] = 2
M
```

#### Fill in matrix M
```{r}
for(i in 2:nrow){
  for(j in 2:ncol){
    h_score = M[i,j-1] + score[3]
    v_score = M[i-1,j] + score[3]
    if(coln[j] == rown[i]) d_score = M[i-1,j-1] + score[1]
    else d_score = M[i-1,j-1] + score[2]
    x = c(h_score,v_score,d_score)
    M[i,j] = max(x)
    move[i,j] = which(x == M[i,j])[1]
  }
}
M
```

#### Tracing back to find the alignment
```{r}
alignment = matrix("",nrow=2,ncol=nrow+ncol)
i = nrow
j = ncol
x = move[i,j]
index = nrow+ncol
while(x != 0){
  if(x == 3) {
    alignment[1,index] = coln[j]
    alignment[2,index] = rown[i]
    i = i-1
    j = j-1
    index = index-1
  }else if(x == 2){
    alignment[1,index] = "-"
    alignment[2,index] = rown[i]
    i = i-1
    index = index-1
  }else{
    alignment[1,index] = coln[j]
    alignment[2,index] = "-"
    j = j-1
    index = index-1
  }
  x = move[i,j]
}

```

#### Show the alignment
```{r}
alg=rep("",2)
alg[1]=paste(alignment[1,], collapse="")
alg[2]=paste(alignment[2,], collapse="")

result = list(M=as.matrix, score = as.numeric, alignment=as.character)

result$M = M
result$score = M[nrow,ncol]
result$alignment = alg
result
```

#### A wrapper function for Needleman-Wunch algorithm
```{r}
Needleman_Wunch <- function(seq1, seq2, score){
  ncol = nchar(seq1)+1
  nrow = nchar(seq2)+1

  #create matrix M
  M = matrix(0, ncol = ncol, nrow = nrow)
  colnames(M) = c("",unlist(strsplit(seq1,split="")))
  rownames(M) = c("",unlist(strsplit(seq2,split="")))
  
  coln = c("",unlist(strsplit(seq1,split="")))
  rown = c("",unlist(strsplit(seq2,split="")))
  
  move = M
  
  #fill in the first row and first column of M,N
  for(i in 2:ncol) M[1,i] = M[1,i-1] + score[3]
  for(i in 2:nrow) M[i,1] = M[i-1,1] + score[3]
  
  for(i in 2:ncol) move[1,i] = 1
  for(i in 2:nrow) move[i,1] = 2
  
  #fill in M
  for(i in 2:nrow){
    for(j in 2:ncol){
      h_score = M[i,j-1] + score[3]
      v_score = M[i-1,j] + score[3]
      if(coln[j] == rown[i]) d_score = M[i-1,j-1] + score[1]
      else d_score = M[i-1,j-1] + score[2]
      x = c(h_score,v_score,d_score)
      M[i,j] = max(x)
      move[i,j] = which(x == M[i,j])[1]
    }
  }
  
  alignment = matrix("",nrow=2,ncol=nrow+ncol)
  i = nrow
  j = ncol
  x = move[i,j]
  index = nrow+ncol
  while(x != 0){
    if(x == 3) {
      alignment[1,index] = coln[j]
      alignment[2,index] = rown[i]
      i = i-1
      j = j-1
      index = index-1
    }else if(x == 2){
      alignment[1,index] = "-"
      alignment[2,index] = rown[i]
      i = i-1
      index = index-1
    }else{
      alignment[1,index] = coln[j]
      alignment[2,index] = "-"
      j = j-1
      index = index-1
    }
    x = move[i,j]
  }
  
  alg=rep("",2)
  alg[1]=paste(alignment[1,], collapse="")
  alg[2]=paste(alignment[2,], collapse="")
  
  result = list(M=as.matrix, score = as.numeric, alignment=as.character)  
  result$M = M
  result$score = M[nrow,ncol]
  result$alignment = alg  
  result
}

seq1="ATTCCTGTTCCCGTC"
seq2="ATCCTGCGTTCGTC"
Needleman_Wunch(seq1,seq2,score=c(1,-1,-1))
```


