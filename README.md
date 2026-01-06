# Theorie

De volgende onderwerpen zullen worden besproken:
Theorie bestaat uit de volgende onderwerpen

1. Basis Datastructuren en complexiteit
2. Graphs en bomen (Trees)
3. Numpy en data begrijpen / analyseren
4. Data representaties
5. Unsupervised learning
6. Supervised Learning
7. Neurale Netwerken (NN) Intro
8. Beslissingsbomen (Descision trees)

Op zoek naar meer detail over de **onderwerpen** die we gaan bespreken? 
Die kun je [HIER](https://github.com/hogeschool/Machine-Learning-Basics-public/blob/main/theory.md) vinden.

---
# Project

**Opdracht: Handgeschreven Cijferherkenning op een NumberDigitalizer**

Een fictief bedrijf heeft een apparaat ontwikkeld dat **NumberDigitalizer** heet. Het apparaat heeft een klein schermpje waar de gebruiker een handgeschreven getal kan invoeren met een stylo pen. Het getal moet worden omgezet naar een digitale representatie getal en doorgegeven aan een gekoppeld apparaat.

Het apparaat NumberRecoDigitalizer ziet er zo uit:
[![Alt text](https://github.com/hogeschool/Machine-Learning-Basics-public/blob/main/mystery_device.png)](https://github.com/hogeschool/Machine-Learning-Basics-public/blob/main/mystery_device.png)


***NumberDigitalizer apparaat concept***

**Scenario:**

Je wordt gevraagd om een handgeschreven cijferherkenningssysteem voor een NumberDigitalizer met de volgende (vaste) hardware requirements:

- Een scherm met een resolutie van 28 bij 28 pixels
- Zeer beperkt RAM (~256 KB)
- Beperkte opslag (~1 MB voor programma + model)
- Geen GPU

Je doel is om een model te trainen (op MNIST database) dat efficiënt draait op dit apparaat, waarbij het geheugenverbruik en de rekentijd zo klein mogelijk worden gehouden.

**Onderzoek**
Alvorens aan de slag te gaan doe je eerst een onderzoek naar de beschikbare trainingsdata en de tools.

Vervolgens probeer je met algoritmes tot een oplossing te komen en kijk je wat de meestgeschikte algoritmes zijn:
- K means clustering
- Linear Regression
- Decision Tree
- Neuraal Netwerk


## Onderzoek

**Beschrijving: Onderzoek eerst hoe de data er uit ziet**

De onderwerpen die daarbij aan bod komen zijn:
- Datastructuren (gebruik oa Numpy)
- Visualisatie
- PCA
- Nadenken over algoritmekeuze. Bijvoorbeeld activatiefunctie van een Neuraal netwerk, architectuur etc.

- Nadenken over ideeen voor optimalisatie. Enkele voorbeelden:
    - Comprimeren van MNIST images: uint8 → uint4 of binair (0 of 1).
    - Flat arrays vs nested arrays voor gewichten.
    - Mini-batches als queue of ringbuffer.
    - etc.

## Simpele feature extraction

**Beschrijving: Maak een paar simpele features van de 28×28 afbeelding:**

***Waarom interessant?***

De studenten kunnen eerst gewend raken aan de data, experimenteren met data en kijken of ze aan de hand van features het getal kunnen voorspellen.

- Aantal donkere pixels in kwadranten

- Som van rijen/kolommen

- Aspect ratio van zwarte pixels

- Combinatie van deze of andere features

- Later te combineren met bijvoorbeeld decision tree

## K-means clustering / prototype-based classification

**Beschrijving: Groepeer de cijfers in clusters en gebruik de centroids als representanten.**

***Waarom interessant?***

Studenten leren vectorrepresentaties van data en geheugenbesparing (alleen clustercentroids opslaan i.p.v. volledige dataset).

Studenten zien het effect van het aantal clusters op classificatie-accuracy en geheugen.

Combineer makkelijk met een dict of array-based datastructuur.

***Uitbreiding: Experimenteer met Laplace smoothing en memory-efficient opslag (bijv. floats naar uint8 log-probs).***

## Linear classifier / perceptron

**Beschrijving: Eén laag lineaire classificatie, eventueel met sigmoid/softmax.**

Het basis idee zou kunnen zijn:

Je maakt 10 afzonderlijke lineaire classifiers:

- Perceptron 0: “Is dit cijfer 0 of niet?”

- Perceptron 1: “Is dit cijfer 1 of niet?”

***Waarom interessant?***

- Studenten zien direct gewichten + biases in datastructuren.

- Studenten denken na over eventuele activatiefuncties: eigen of softmax

- Studenten denken na over datarepresentatie

Bijvoorbeeld als een matrix W = [10 × 784] en
b = [b_0, b_1, ..., b_9]

- Lijkt op een mini-neuraal netwerk zonder hidden layers.


## Decision Tree

**Beschrijving: Classificeer een cijfer door een boom van beslissingen op features te doorlopen.**

Bijvoorbeeld: “is het gemiddelde pixelwaarde > 128?” → ja/nee → volgende node → … → klasse.

***Waarom interessant:***

- Studenten leren datastructuren voor boomrepresentatie:

    - Nested dicts of objects voor nodes

    - Flat array / list representation (bijvoorbeeld heap-achtige structuur)

- Ze zien direct memory vs tree depth tradeoff: diepe bomen = veel nodes = veel geheugen, korte bomen = slechtere accuracy.

- Gemakkelijk te combineren met features ipv volledige 28×28 input om geheugen te besparen.

**Extra aandachtspunten / variaties:**

- Gebruik gini of entropy als splitsingscriterium.

- Experimenteer met max depth en min samples per leaf.

- Vergelijk recursive vs iterative tree traversal voor runtime geheugenbesparing.

- Mogelijk gebruik van pruning om geheugen te besparen.

Laat de studenten nadenken over geheugen en snelheid.

Geheugen: klein tot medium, afhankelijk van aantal nodes en feature-representatie.

Snelheid: snel bij kleine bomen, kan trager worden bij grote diepe bomen.

## Neuraal Netwerk

**Beschrijving: Maak een Multi-layer perceptron (MLP) met input layer (28×28 = 784), 1 of 2 hidden layers en otput layer van 10 nodes (cijfers 0-9).**

***Waarom interessant?***

- Studenten leren verschillende datastructuren voor gewichten en biases:

    - Dict van arrays (W1, b1, …)

    - Class met attributes

    - Flat array + offsets

- Ze kunnen experimenteren met activatie functies: ReLU, sigmoid, softmax.

- Memory management wordt belangrijk: grotere hidden layers = meer geheugen, batch size beïnvloedt runtime.

- Laat studenten nadenken over forward pass vs backpropagation: wat moet in geheugen blijven, wat kan hergebruikt worden?

***Extra aandachtspunten / variaties:***

- Experimenteer met verschillende hidden layer groottes (bijv. 32, 64, 128 nodes) en kijk hoe geheugen en accuracy veranderen.

- Gebruik float16 of quantization om geheugen te besparen.

Laat ze ook hier nadenken over het geheugen en snelheid:

Geheugen: relatief groot, afhankelijk van hidden layers en batch size.

Snelheid: redelijk snel voor kleine MLP’s op CPU, geen GPU vereist.

## Andere Algoritmes:

De studenten denken na over andere ideeen en aanpakken : Naive Bayes, Logistic regression, Hashing, lookup-table en andere methoden.


## Ideeen voor vergelijkingen en conclusie (Verplicht):
Ze moeten de geiplementeerde aanpakken k means/ linear regression / Decision Tree / Neural Network vergelijken op dezelfde subset van MNIST:
- Accuracy
- Geheugenverbruik
- Trainingstijd
- Datastructuurcomplexiteit

Dat geeft een praktisch gevoel voor de trade-offs van algoritmes vs datastructuren en uiteindelijk zou moeten leiden tot de beste keuze voor dit probleem. 

