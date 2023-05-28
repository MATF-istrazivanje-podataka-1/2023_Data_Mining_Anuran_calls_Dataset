# Istraživanje skupa podataka "Anuran Calls"
Svrha rada je demonstracija metoda klasifikacije, klasterovanja i pravila pridruživanja različitih vrsta žaba koristeći snimljene audio zapise njihovih oglašavanja. 

Podaci koji su korišćeni su preuzeti sa [linka](https://archive-beta.ics.uci.edu/dataset/406/anuran+calls+mfccs). 

Ovaj skup podataka korišćen je u nekoliko klasifikacionih zadataka koji se odnose na prepoznavanja vrsta žaba na osnovu njihovih poziva. Kreiran je segmentacijom 60 audio zapisa jedinki koje pripadaju 4 različitim porodicama, 8 rodova i 10 vrsti. Svaki audio zapis odgovara jednom primerku (individualnoj žabi), a ID zapisa je takođe uključen u skup podataka kao atribut. Za detekciju audio okvira koji pripadaju svakom slogu korišćena je spektralna entropija i binarna metoda klasterovanja. Segmentacija i ekstrakcija karakteristika su izvršene u Matlabu. Nakon segmentacije, dobijeno je 7195 slogova koji su postali instance za obučavanje i testiranje klasifikatora.

## Metodologija
Izvršena je eksplorativna analiza i vizuelizacija podataka koristeći biblioteke [matplotlib](https://matplotlib.org/), [seaborn](https://seaborn.pydata.org/) i [plotly](https://plotly.com/). Nakon toga izvršeno je pretprocesiranje podataka pomoću biblioteka [pandas](https://pandas.pydata.org/) i [scikit-learn](https://scikit-learn.org/stable/). Pretprocesiranje je rađeno u skladu sa zahtevima klasifikacije i klasterovanja. Poslednji korak je primena različitih metoda klasifikacija, klasterovanja i pravila pridruživanja.

## Korišćeni algoritmi
### Klasifikacija
1. Stablo odlučivanja ([Decision Tree](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html))
2. Slučajna šuma ([Random Forest](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html))
3. K najbližih suseda ([K Nearest Neighbors](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html))
4. Pakovanje ([Bagging](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.BaggingClassifier.html))
5. Gausov naivni Bajes ([Gaussian Naive Bayes](https://scikit-learn.org/stable/modules/generated/sklearn.naive_bayes.GaussianNB.html))
### Klasterovanje
1. K sredina ([K-means](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html))
2. Hijerarhijsko klasterovanje ([Agglomerative](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.AgglomerativeClustering.html))
3. DBSCAN ([DBSCAN](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.DBSCAN.html))
### Pravila pridruživanja
1. Apriori
2. FP-Growth
