# SSR PFE
Academical project done in SSR classes at Telecom SudParis, its focus is on the study of anonymity in blockchain field, especially by reproducing a mixer on Tezos blockchain.
# FAQ
- [Tornado.cash est-il basé sur un seul Smart Contract ? Le SC étant géré par la même entité intermédiaire (représentant Tornado.cash?).](#smart-contracts-de-tornado-cash)
- [Comment sont-il crééés les pools et comment faire entrer des users (je me rappelle que vous avez expliqué rapidement cela, mais à travers ma question, je voulais savoir s'il y a eu une pré-authentification/validation des crédentials du user qui veut rentrer dans le pool?).](#entree-et-sorties-de-la-pool)
- [Comment sont-ils élus les validateurs (est ce que c'est ouvert? ou c'est géré totalement par Tornado.cash?).](#centralisation-de-tornado-cash)

Si la gestion est totalement maitrisée par Tornado.cash, on risque d'avoir un problème de vie privée/identification par Tornado.cash aux utilisateurs de ce service. => En faite, cette réflexion vient du faite qu'en utilisant Tornado.cash,; nous avons l'impression de se baser sur une blockchain privée (géré de façon centralisée par Tornado.cash) imbriquée dans une blockchain publique.

## Smart Contracts de Tornado Cash
Tornado.cash base sa logique sur plusieurs contrats (https://github.com/tornadocash/tornado-core/tree/master/contracts) ; l'un d'eux est celui du jeton ERC-20 associé. Toutefois, il est certainement possible de tout réunir dans un même contrat pour limiter les frais de transaction (les appels inter-contrats coûtent cher en termes de gas).

## Entree et sorties de la pool
Les pools sont des contrats déployés par Tornado.cash, chaque pool a son propre contrat (et son propre arbre de Merkle).
Chaque utilisateur entre dans une pool après avoir généré une note (le hash de deux randoms k et r générés côté client)

## Centralisation de Tornado Cash
Les validateurs vérifient les transactions effectuées sur le réseau Ethereum ; ils peuvent être totalement indépendants de Tornado.cash. 
