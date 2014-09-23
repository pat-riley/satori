# L-System

A Lindenmayer System is a parallel rewriting system and a type of formal grammar. An L-System consists of an alphabet of symbols that can be used to make strings, a collection of production rules that expand each symbol into a larger string of symbols.

## Origins 

As a biologist, Lindenmayer worked with yeast and filamentous fungi and studied the growth patterns of various types of algae, such as the blue/green bacteria Anabaena catenula. Originally the L-systems were devised to provide a formal description of the development of such simple multicellular organisms, and to illustrate the neighbourhood relationships between plant cells. Later on, this system was extended to describe higher plants and complex branching structures.

## Structure

The recursive nature of the L-system rules leads to self-similarity and thereby, fractal-like forms are easy to describe with an L-system. Plant models and natural-looking organic forms are easy to define, as by increasing the recursion level the form slowly 'grows' and becomes more complex. Lindenmayer systems are also popular in the generation of artificial life.

## Example 1: Algae

Lindenmayer’s original L-System for modeling the growth of algae.

#### Variables:
A B
#### Constants: 
none
#### Start: 
A
#### Rules:
(A → AB) , (B → A)

which produces:
```
n = 0 : A
n = 1 : AB
n = 2 : ABA
n = 3 : ABAAB
n = 4 : ABAABABA
n = 5 : ABAABABAABAAB
n = 6 : ABAABABAABAABABAABABA
n = 7 : ABAABABAABAABABAABABAABAABABAABAAB
```


```
n=0:         A           start (axiom/initiator)
            / \
n=1:       A   B         
          /|    \
n=2:     A B     A       
        /| |     |\
n=3:   A B A     A B     
      /| | |\    |\ \
n=4: A B A A B   A B A   
```

If we count the length of each string, we obtain the famous Fibonacci sequence of numbers (skipping the first 1, due to our choice of axiom):
```
1 2 3 5 8 13 21 34 55 89 ...
```

For each string, if we count the k-th position from the left end of the string, the value is determined by whether a multiple of the golden ratio falls within the interval (k-1, k). The ratio of A to B likewise converges to the golden mean.

This example yields the same result (in terms of the length of each string, not the sequence of As and Bs) if the rule (A → AB) is replaced with (A → BA), except that the strings are mirrored.

This sequence is a locally catenative sequence because G(n)=G(n-1)G(n-2), where G(n) is the n-th generation.