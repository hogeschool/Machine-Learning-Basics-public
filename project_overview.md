**Project: Basic Machine Learning Algorithms for recognition of numbers on an embedded device with limited capabilities** 


**Language: Python**  

Focus: Exploration of if given data. Implementation and application of at least two supervised learning techniques while choosing correct datastructures and algorithmic functions. 
 

**Purpose** 

Studets with experiment with the given dataset. Students will create and experience at least two supervised learning approaches (decision tree and a neural network) without the use of external libraries to run with a minimal resource allocation on a simulated embedded device with limited capabilities.  

They will experiment with different options and experience the importance of the choices they make during implementation. 


## Gedetaillerd

# Project

**Opdracht: Handgeschreven Cijferherkenning op een NumberRecogneDigitalizer**

Een fictief bedrijf heeft een apparaat ontwikkeld dat NumberRecogneDigitalizer heet. Het apparaat heeft een klein schermpje waar de gebruiker een handgeschreven getal kan invoeren met een stylo pen. Het getal moet worden omgezet naar een digitale representatie getal en doorgegeven aan een gekoppeld apparaat.

Het apparaat NumberRecoDigitalizer ziet er zo uit:
[![Alt text](https://github.com/hogeschool/Machine-Learning-Basics-public/blob/main/mystery_device.png)](https://github.com/hogeschool/Machine-Learning-Basics-public/blob/main/mystery_device.png)


***Handwritten digit device***

**Scenario:**

Je wordt gevraagd om een handgeschreven cijferherkenningssysteem voor een NumberRecogneDigitalizer met:

Een scherm met een resolutie van 28 bij 28 pixels
Zeer beperkt RAM (~256 KB)
Beperkte opslag (~1 MB voor programma + model)
Geen GPU
Je doel is om een model te trainen (op MNIST) dat efficiënt draait op dit apparaat, waarbij het geheugenverbruik en de rekentijd zo klein mogelijk worden gehouden.

**Onderzoek**
Alvorens aan de slag te gaan doe je eerst een onderzoek naar de beschikbare trainingsdata en de tools.
Vervolgens proberen de studenten de volgende algoritmes uit om tot een oplossing te komen.

## K-nearest neighbors (KNN)

**Beschrijving: Classificeer een nieuw cijfer op basis van de meest vergelijkbare cijfers uit de training set.**

***Waarom interessant voor deze opdracht:***

Studenten moeten nadenken over efficiënte opslag van trainingsdata (bijv. flattenen van 28×28 pixels naar een 784-vector, of compressie via uint8).

Geheugen vs snelheid tradeoff: volledige dataset bewaren kost veel RAM → kleine subset of quantization nodig.

Mogelijkheid om verschillende datastructuren voor snelle zoekopdrachten te proberen:
- Gewone lijst
- K-D tree
- Ball tree

Kan direct getest worden op subsets van MNIST.
***Uitbreiding: Experimenteer met verschillende afstandsfuncties: Euclidean, Manhattan, Cosine.***

## K-means clustering / prototype-based classification

**Beschrijving: Groepeer de cijfers in clusters en gebruik de centroids als representanten.**

Waarom interessant:

Studenten leren vectorrepresentaties van data en geheugenbesparing (alleen clustercentroids opslaan i.p.v. volledige dataset).

Studenten zien het effect van het aantal clusters op classificatie-accuracy en geheugen.

Combineer makkelijk met een dict of array-based datastructuur.

Naive Bayes (pixel-based)

Beschrijving: Klassificeer op basis van de waarschijnlijkheid dat een pixel aan/uit is gegeven het cijfer.

Waarom interessant:

Ze zien dat binair of discretized data geheugen kan besparen.

Studenten moeten nadenken over datastructuur van parameters (probabiliteiten per pixel × klasse → matrix van 28×28×10).

Minimalistische implementatie, kan met weinig geheugen.

Uitbreiding: Experimenteer met Laplace smoothing en memory-efficient opslag (bijv. floats naar uint8 log-probs).

## Linear classifier / perceptron

Beschrijving: Eén laag lineaire classificatie, eventueel met sigmoid/softmax.

Waarom interessant:

Studenten zien direct gewichten + biases in datastructuren.

Lijkt op een mini-neuraal netwerk zonder hidden layers.

Kan gecombineerd worden met batch updates of stochastic gradient descent.

## Simple feature extraction + small tree/linear classifier

Beschrijving: Maak een paar simpele features van de 28×28 afbeelding:

Aantal donkere pixels in kwadranten

Som van rijen/kolommen

Aspect ratio van zwarte pixels

Combineer deze features met:

Decision tree

## Naive Bayes

Logistic regression

Waarom interessant:

Studenten leren datastructuren voor feature opslag.

Meer abstractie → minder geheugen.

Ze zien dat simpele features al behoorlijk goed kunnen zijn voor MNIST.

## Hashing / lookup-table methoden

Beschrijving: Voor kleine subsets van MNIST kunnen ze een hash van de 28×28 binarized image maken → direct lookup van label.

Waarom interessant:

Studenten oefenen met hash tables / dicts en geheugenoptimalisatie.

Leert hen tradeoff tussen precomputatie vs runtime opslag.

Beperking: werkt vooral op zeer kleine subset van trainingsdata.

## Decision Tree

Beschrijving:
Classificeer een cijfer door een boom van beslissingen op features te doorlopen. Bijvoorbeeld: “is het gemiddelde pixelwaarde > 128?” → ja/nee → volgende node → … → klasse.

Waarom interessant:

Studenten leren datastructuren voor boomrepresentatie:

Nested dicts of objects voor nodes

Flat array / list representation (bijvoorbeeld heap-achtige structuur)

Ze zien direct memory vs tree depth tradeoff: diepe bomen = veel nodes = veel geheugen, korte bomen = slechtere accuracy.

Gemakkelijk te combineren met features ipv volledige 28×28 input om geheugen te besparen.

Extra aandachtspunten / variaties:

Gebruik gini of entropy als splitsingscriterium.

Experimenteer met max depth en min samples per leaf.

Vergelijk recursive vs iterative tree traversal voor runtime geheugenbesparing.

Mogelijk gebruik van pruning om geheugen te besparen.

Geheugen & snelheid (indicatief):

Geheugen: klein tot medium, afhankelijk van aantal nodes en feature-representatie.

Snelheid: snel bij kleine bomen, kan trager worden bij grote diepe bomen.

## Neural Network

Beschrijving:
Multi-layer perceptron (MLP) met input layer (28×28 = 784), 1 of 2 hidden layers en output layer van 10 nodes (cijfers 0-9).

Waarom interessant:

Studenten leren verschillende datastructuren voor gewichten en biases:

Dict van arrays (W1, b1, …)

Class met attributes

Flat array + offsets

Kunnen experimenteren met activatie functies: ReLU, sigmoid, softmax.

Memory management wordt belangrijk: grotere hidden layers = meer geheugen, batch size beïnvloedt runtime.

Laat studenten nadenken over forward pass vs backpropagation: wat moet in geheugen blijven, wat kan hergebruikt worden?

Extra aandachtspunten / variaties:

Experimenteer met verschillende hidden layer groottes (bijv. 32, 64, 128 nodes) en kijk hoe geheugen en accuracy veranderen.

Mini-batch training met ringbuffer/queue om RAM te besparen.

Random gewichten initieel, daarna implementatie van backpropagation en gradient updates.

Gebruik float16 of quantization om geheugen te besparen.

Geheugen & snelheid (indicatief):

Geheugen: relatief groot, afhankelijk van hidden layers en batch size.

Snelheid: redelijk snel voor kleine MLP’s op CPU, geen GPU vereist.


# Onderzoek eerst hoe de data er uit ziet.
Numpy
Visualisatie
PCA
Descision Tree
NN

## Ideeen voor optimalisatie:
Comprimeren van MNIST images: uint8 → uint4 of binair (0 of 1).
Flat arrays vs nested arrays voor gewichten.
Mini-batches als queue of ringbuffer.

## Ideeen voor vergelijkingen:
Ze kunnen de aanpakken Decision Tree en Neural Network vergelijken op dezelfde subset van MNIST:
Accuracy

Geheugenverbruik

Trainingstijd

Datastructuurcomplexiteit

Dat geeft een praktisch gevoel voor de trade-offs van algoritmes vs datastructuren. 