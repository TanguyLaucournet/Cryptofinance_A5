# Cryptofinance_A5

Etude de différents type d'attaque sur Bitcoin

## OneTwoAttack 

Attaque simple fonctionnant par cycle de 3 blocks au termes desquels l'attaquant est gagnant si il possède plus de block que la blockchain officielle

La fonction permettant de simuler l'attaque prend en paramètre deux attributs qui sont n, le nombre de cycle et q le hashrate de l'attaquant.
En prenant n = 10000 et q variant de 0 à 0.5 par intervalle de 0.005 nous arrivons à ce resultat:

![image](https://user-images.githubusercontent.com/40137577/151869263-87b9d51f-a305-4881-ba75-45db274b732a.png)

Ici nous trouvons que l'attaque est rentable à partir de 0.405 de hashrate

## DoubleDepense

Attaque consistant à faire accepter une transaction faite par le seuil de z block de confirmation pour ensuite remplacer ces blocks

La fonction permettant de simuler l'attaque à le double dépense prend en paramètre: 
n le nombre d'attaque
q le hashrate de l'attaquant
z le nombre de blocks de confirmation nécessaire pour que le paiement soit accepté
a le seuil à partir duquel l'attaquant stop de peur de se faire rattraper par la blockchain officielle
premined le nombre de block d'avance qu'a l'attaquant au début de l'attack

Avec n = 10000, a = 3 , premined 1 et q variant de 0 à 0.5 par intervalle de 0.005 nous arrivons à ces resultats en fonction de z:

![image](https://user-images.githubusercontent.com/40137577/151869440-667ff342-4b12-4b3c-a7cb-c58c7d1a3cde.png)

## MinageOptimal

Attaque cherchant à maximiser le gain de l'attaquant au cours d'un cycle d'attaque dépendant de différents attributs

Ici nous utilisons un fonction récursive prenant comme paramètre:
    q = hashrate de l'attaquant
    n = nombre de block lors d'une attaque
    c = cout
    a = nb de blocks de l'attaquant 
    h = nb de blocks de la blockchain officielle
 Avec q variant de 0 à 0.5 par intervalle de 0.005 nous arrivons à ces resultats en fonction de n: 
( Ici nous considérons que le cout est équivalent au hashrate)
![image](https://user-images.githubusercontent.com/40137577/151869447-10291d43-7621-4613-9d6e-51ec08031cb2.png)


## SelfishMining

Répétition de la stratégie de minage égoiste en fonction de différents attributs

La fonction permettant de simuler le slefish mining prend comme paramètre 
     q = hashrate de l'attaquant
     gamma = connectivité de l'attaquant, cela correspond, lorsque que l'attaquant perd son avance sur la blockchain officielle et qu'il publie tout de même ses blocks, à la          chance que le prochain block miné par quelqu'un le soit sur le block de l'attaquant
     n = nombre de simulations
  
En prenant n = 10000 et q variant de 0 à 0.5 par intervalle de 0.005 nous arrivons à ces resultats en fonction de gamma:
![image](https://user-images.githubusercontent.com/40137577/151869450-5accb5ba-a405-453e-901a-9a1e95e403fa.png)


