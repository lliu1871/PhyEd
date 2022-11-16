---
layout: markdown
title: Tree traversal
permalink: /code/traversal/
author: "Liang Liu"
output: html_document
date: 2021-04-16
---

# {{ page.title }}

#### check if a tree is rooted

```{python}
tree1 = "((((s1,s2),s3),s4),s5);"
tree2 = "(((s1,s2),s3),s4,s5);"

is.rooted = function(treestring){
	character = unlist(strsplit(treestring,split=""))

	comma = sum(character==',')
	leftp = sum(character=='(')

	if(comma == leftp){
		rooted=TRUE
	}else{
		rooted=FALSE
	}
	rooted
}
```

#### find the offspring species of an internal node
```
library(phybase)
tree=read.tree.nodes(tree1)
species = tree$names
nspecies = length(species)
nodes = tree$nodes


find_offspring = function(inode, treenodes, taxanames, nspecies, offspring){
	if(inode <= nspecies){
		offspring[inode] = 1
		return (offspring)
	}else{
		son1 = treenodes[inode,2]
		son2 = treenodes[inode,3]
		offspring = find_offspring(son1, treenodes, taxanames, nspecies, offspring)
		offspring = find_offspring(son2, treenodes, taxanames, nspecies, offspring)
	}
	return (offspring)
}

offspring1 = rep(0,nspecies)
find_offspring(inode=7, nodes, species, nspecies, offspring1)

inor = rep(0, dim(nodes)[1])
index=1
```

#### Inorder traversal
```
inorder = function(inode, treenodes, nspecies){
	if(inode <= nspecies){
		print(inode)
		inor[index] <<- inode
		index<<-index+1
	}else{
		left = treenodes[inode,2]
		right = treenodes[inode,3]
		inorder(left, treenodes, nspecies)	
		print(inode)
		inor[index] <<- inode
		index<<-index+1
		inorder(right, treenodes, nspecies)	
	}
}

inorder(9, nodes, nspecies)
```

#### Preorder traversal

```
preorder = function(inode, treenodes, nspecies){
	if(inode <= nspecies){
		print(inode)
	}else{
		left = treenodes[inode,2]
		right = treenodes[inode,3]
		print(inode)
		preorder(left, treenodes, nspecies)	
		preorder(right, treenodes, nspecies)
				
	}
}


preorder(9, nodes, nspecies)
```

#### Postorder traversal

```
postorder = function(inode, treenodes, nspecies){
	if(inode <= nspecies){
		print(inode)
	}else{
		left = treenodes[inode,2]
		right = treenodes[inode,3]
		postorder(left, treenodes, nspecies)	
		postorder(right, treenodes, nspecies)
		print(inode)		
	}
}

postorder(9, nodes, nspecies)

```


