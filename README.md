# Problem-1
Given the binary tree in the image below, use a built in python data structure to represent the binary tree and easy to find any nodes within a given interval (say: find all nodes that have a value between 23 and 68).

def DepthFirst(k, a, b, noduri, l, p):
    '''
    k reprezinta nodul din care pornim
    [a, b] intervalu
    noduri-nr de noduri
    l - lista cu muchii
    p - lista in care salvam nodurile prin care am trecut o data
    '''
    p[k] = 1
    if(k >= a and k <= b):
        print(k) #daca nodul se afla in intervalul [a,b] il afisam
    for i in range(1, noduri + 1):
        if((k,i) in l and p[i] == 0): #daca din nodul k putem ajunge in nodul i si nu am mai trecut prin nodul i apelam recursiv pt i
            DepthFirst(i, a, b, noduri, l, p)
noduri = int(input("Introduceti numarul de noduri:")) #numarul de noduri
muchii = int(input("Introduceti numarul de muchii:")) #numarul de muchii
l = []
for i in range(0, muchii):
    x, y = int(input()), int(input())
    l.append((x, y)) #salvarea muchilor in lista dupa citire
lista = (noduri + 1) * [0] #initializare lista
DepthFirst(1, 23, 68, noduri, l, lista) #apelarea functiei DepthFirst care rezolva probelma
