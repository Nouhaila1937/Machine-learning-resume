# Machine-learning-resume
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
