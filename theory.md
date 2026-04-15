## 1.1 Basic Data Structures

**L1.1.1** Kunnen uitleggen wat complexiteit is, met name O(1), O(n), O(n^2) en O(log(n)).

**L1.1.2** Werking van de volgende datastructuren kunnen uitleggen en toepassen:
- List
- Tuple
- Dictionary
- Set
- Stack
- Queue
- Linked List

**L1.1.3** De complexiteit van bovengenoemde structuren kunnen uitleggen

## 1.2 Trees

**L1.2.1**
- Weten wat dot product is en hoe je deze met de hand kan berekenen op vectoren
- Weten wat de uitkomst betekent (vergelijkbare richting, loodrecht of tegenovergesteld) 

**L1.2.2**
- Weten wat slicing betekent
- Wat is het verschil tussen copy en view (in Numpy)

**L1.2.3**
- definitie, werking en complexiteit begrijpen van een binaire boom
- definitie, werking en complexiteit begrijpen van een binaire zoekboom
(rotaties hoef je niet zelf uit te voeren, wel begrijpen waarom)
- volgende termen begrijpen en uitleggen: 
    - hoogte van een boom bepalen
    - perfect binary tree 
    - full binary tree
    - balanced binary tree 
    - complete binary tree

## 1.3 Graphs

**L1.3.1**
- definitie, werking begrijpen van een graaf
- definities kennen van de termen die bij ene graf horen (ie node, directed, weighted etc.)

**L1.3.2**
- Breadth‑First Search begrijpen en kunnen toepassen

**L1.3.3**
- Depth‑First Search begrijpen en kunnen toepassen

**L1.3.4**
- Dijkstra algoritme en A* begrijpen en kunnen toepassen

**L1.3.5**
- Begrijpen wanneer je voor een van de besproken zoekmethodes kiest

**L1.3.6**
- priority queue en Min/max heap kunnen uitleggen

**L1.3.7**
- Manhattan distance en Eclidean distance kunnen uitleggen en toepassen    

## 2.1 Data Representation

**L2.1.1**
- Volgende termen / type data / features kunnen uitleggen:
  Categorical, numerical, discrete, continuous, nominal, ordinal.
- indien data is gegeven kunnen beargumenteren welke termen van toepassing zijn  

**L2.1.2**
- Begrijpen waaom encoderen belangrijk is voor categorical data
- Ordinal Encoding begrijpen en kunnen toepassen
- One Hot Encoding begrijpen en kunnen toepassen

**L2.1.3**
- Begrijpen waarom encoderen belangrijk is voor numerieke data
- Normalisatie kunnen toepassen

**L2.1.4**
- Binning types begrijpen: Equal‑Width Binning, Equal‑Frequency    Binning, Semantic Binning
- Binning kunnen toepassen en uitleggen wanner je voor welke kiest

**L2.1.5**
- Weten waar RGB RGBA CYMK en HSV/HSB voor staan en wanneer je ze beter toe kan passen. 

## 2.2 Unsupervised Learning

**L2.2.1**

Redenen Unsupervised Learning kunnen uitleggen

**L2.2.2**

Covariantie matrix kunnen lezen en samenhang tussen variabelen kunnen inzien

**L2.2.3**

Nut van PCA kunnen begrijpen en uitleggen wat het is. Begrijpen waar PC1 en PC2 voor staan in een 2D PCA grafiek. Je hoeft de transformatie formules niet zelf te kennen/berekenen.

**L2.2.4**

K-means clustering:

- Begrijpen waar K means clustering voor gebruikt kan worden
- Het proces (de stappen) van K means clustering kunnen uileggen
- Begrijpen hoe in de stappen van het proces de afstanden en gemiddelden berekend worden
- Begrijpen wat een centroid en een prototype is 
- Begrijpen wat de mogelijke voor/nadelen zijn van verschillende K waardes toegepast op een dataset

**L2.2.5**

Association rule learning

- Begrijpen waar we associateregels voor gebruiken
- De termen Support en Support Count kunnen uitleggen
- Support en Support Count kunenn berekenen gegeven een dataset
- Confidence en Lift kunnen berekenen als de formules zijn gegeven: je hoeft dus voor Confidence en Lift de formules niet uit je hoofd te leren, wel kunnen toepassen
- Weten wat de waarde van Lift betekent voor een associatieregel: Lift > 1, Lift < 1 en Lift = 1


## 2.3 Supervised Learning

**L2.3.1**

- Redenen Supervised Learning kunnen uitleggen.
- Begrijpen wat het verschil is tussen classification en regression

**L2.3.2**

Lineaire regressie:
- Kunnen uitleggen wat het is
- Een lijn kunnen schatten in een 2d grafiek (zonder wiskunde). 

**L2.3.3**

Convolutie:

- Begrijpen wat het is en waar we het voor kunnen gebruiken
- Kunnen uitleggen wat een kernel is
- Lengte resulterende lijst na kernel verschuiving knnnen berekenen ( W−K+1 )
- Dot Product kunnen berekenen (voor 1D data)
- Een simpele 1D convolutie met de hand kunnen uitvoeren gegeven een kernel (zie presentatie voor voorbeeld)

**L2.3.4**

K Nearest Neighbours:

- Begrijpen hoe het werkt
- Uitleggen wat de invloed is van grotere/kleinere K
- Aan de hand van gegeven data met de hand een classificatie kunnen uitvoeren met verschillende K waardes (zie presentatie voor een voorbeeld)

----
## Proefexamen tot hier!
----


## 2.4 Decision Trees

**L2.4.1**
- De stappen die de decision tree algoritme maakt begrijpen

**L2.4.2**

Gini:

- Begrijpen wat pure/niet pure in deze context betekent
- Gini impurity kunnen berekenen aand e hand van de formule (*eventueel is een rekenmachine toegestaan)
- Kunnen beredeneren hoeveel keer we kunnen splitsen voor een featuregroep gegeven de data
- Gewogen Gini (links/rechts) kunnen berekenen na de splitsing

**L2.4.3**
- Pruning begrijpen en manier van pruning kunnen uitleggen. 

**L2.4.3**
Random forest
- Random forest toepassing kunnen uitleggen
- Bootstrap, random features en maximale groei in deze context kunnen uitleggen


----

## Overige gedetailleerde leerdoelen volgen nog

Globale overzicht (kan nog veranderen):

**Neural Networks Introduction**

- Purpose 

- Introduction to global architecture: Layers, weights, bias etc 

- Forward step 

- Data representation 

- Explore MNIST database (practicum) 

- Experiment with test/train set and data representations (practicum) 

 

**Architecture and data for the NN** 

- Architecture in more detail, why certain choices are made (eg layers, nodes etc.) 

- Introduction to epochs, accuracy and loss 

- Predictions and Evaluations 

- Explanation of using a library to create a simple NN and how to experiment with it 

- Experiment with architectures. Experiment with different data representations. Create a simple Neural Network with a library (practicum) 

 

**Activation functions** 

- Forward propagation 

- activation functions: Relu, Sigmoid, Softmax 

- Implement activation function without external libraries except for numpy: ReLU, Sigmoid, 

- Softmax 

- Start implementing a minimal  NN (without backpropagation): a forward step using activations (practicum) 

- Experiment with different datastructures  (practicum) 

 

**Back propagation** 

- Basic explanation and purpose 

- Gradient 

- Derivative of activation functions 

- Cross-entropy loss 

- Loss derivative 

- Learning rate 

- Backpropagation in depth pseudocode 

- Implement a function to calculate loss and experiment. (practicum) 

- Implement a derivative activation function (practicum) 

- Implement a backpropagation function. (practicum) 

 

**Train and predict** 

- TODO 

- Complete and continue working on your NN and data representation with different data structures and representations (practicum) 

**Mogelijk andere onderwerpen**