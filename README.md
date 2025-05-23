# Machine-learning-resume
soit la régression linéaire simple multiple polynomiale multivarié ou univarié  régression logistique ou autre sont appelés des algorithme de machine learning 


## data split 
![image](https://github.com/user-attachments/assets/c09dbeb7-08a9-4e29-93a0-d20cfb3290dc)
dans cette image on a cette ligne 
```bash
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```
cette fonction doit respecter l'ordre parceque la fonction retourne ceci en ordre
```bash
résultat = train_test_split(X, y, test_size=0.2)
X_train = résultat[0]
X_test = résultat[1]
y_train = résultat[2]
y_test = résultat[3]
```
du coup il faut respecter l'ordre de X_train....
le test_size=0.2 veut dire qu'on garde 20% des données pour faire le test et le 80% restantes pour l'entrainement 
## La normalisation 
La normalisation (ou standardisation) est très importante dans de nombreux cas, mais elle n’est pas toujours obligatoire. Ça dépend de l’algorithme que tu utilises.

## 🔍 Si tu fais la normalisation sans vérifier l’algo :
Voici ce qui peut arriver :
### ✅ Cas 1 : Tu utilises un algo qui a besoin de normalisation
➡️ Par exemple : k-NN, SVM, régression logistique, régression linéaire, etc.
👉 Si tu normalises, c’est parfait ! Tu aides l’algorithme à mieux apprendre (convergence plus rapide, meilleure précision, etc.)
### ✅ Cas 2 : Tu utilises un algo qui n’en a pas besoin
➡️ Par exemple : arbre de décision, random forest, XGBoost, etc.
### 👉 Si tu normalises :
Ce n’est pas grave,
Mais ça ne sert à rien (ça ne change ni les performances ni la logique),
Parfois, ça peut ajouter de la complexité inutile ou ralentir un peu l’entraînement.
Donc pas dangereux, mais pas utile non plus.
### ⚠️ Cas à éviter :
Si tu fais la normalisation après avoir divisé les données, attention à ne pas normaliser sur tout le jeu de données, sinon :
❌ Tu vas fuir l'information du test dans l'entraînement
(Ton modèle "verra" des infos du futur, ce qui est interdit dans le ML)

### La normalisation est faite uniquement sur X_train après le train_test_split().
### 🔄 Ensuite :
On "fit" le scaler sur X_train (c’est-à-dire qu’on calcule la moyenne et l’écart-type de X_train)

Puis on "transforme" :

X_train ✅ (normalisé avec ses propres stats)

X_test ✅ (normalisé avec les stats de X_train, et pas ses propres stats !)

en normalisant les données de test (X_test) en utilisant la moyenne et l'écart-type calculés uniquement sur les données d'entraînement (X_train), on simule une situation où le modèle rencontre des données totalement nouvelles, sans aucune connaissance préalable de leur distribution.




## Accuraccy
ici l'accuracy soit de calculer le R² il est dans la régréssion linéaire 
soit il s'appelle l'accuraccy dans la classification
## Régression linéaire simple:
f(x)=ax1+b

## Régression linéaire multiple:
```
f(x)=ax1+bx2+c
```

## Régression logistic non linéaire

on utilise une fonction qui va nous permettre de transformer les données non linéairement séparables en un espace de caractéristiques où elles peuvent devenir linéairement séparables . Cela permet à des modèles linéaires, comme la régression logistique, de capturer des frontières de décision non linéaires.

## 📊 Visualisation des données
Avant d'appliquer la fonction mapFeature, il est essentiel de visualiser les données pour comprendre leur structure. Si les données sont clairement non linéaires, comme dans le cas de deux classes disposées en cercles concentriques, une frontière linéaire ne suffira pas. C'est dans ce contexte que l'ajout de termes polynomiaux devient pertinent.


```bash
def mapFeature(X1, X2, degree):
    #res = np.ones(X1.shape[0])
    res = np.zeros((X1.shape[0], 0))
    for i in range(1,degree + 1):
        for j in range(0,i + 1):
            res = np.column_stack((res, (X1 ** (i-j)) * (X2 ** j)))
    return res


```
on peut utiliser d'autre méthode :
![image](https://github.com/user-attachments/assets/010f7ca6-e62f-4689-81d7-dc692cf72347)
















