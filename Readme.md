# Transaction : 
Une transaction est un ensemble d'opérations qui doivent être exécutées comme une seule unité. Soit toutes les opérations réussissent, soit aucune ne l'est. Cela garantit la cohérence des données et l'absence d'erreurs partielles.

# Objectifs principaux des transactions:

## Atomicité:
    -Les opérations d'une transaction sont indivisibles. Si une opération échoue, la transaction entière est annulée.
## Cohérence:
    -La transaction maintient la cohérence des données.
## Isolation:
    -Les transactions sont isolées les unes des autres. Les modifications apportées par une transaction ne sont pas visibles par les autres transactions tant que la première n'est pas terminée.
## Durabilité:
    -Les modifications apportées par une transaction validée sont permanentes et ne peuvent pas être perdues.

# Utilisation des transactions:

     Les transactions sont utilisées dans de nombreux types d'applications:
      *applications de base de données, 
      *applications financières
      *applications de commerce électronique.

==> Elles sont essentielles pour garantir la cohérence et l'intégrité des données dans les systèmes distribués.

# Mise en œuvre des transactions en JAVA: 

Il existe deux manières principales de gérer les transactions en Java:

## Programmation par transaction: 
    Vous démarrez manuellement une transaction, exécutez les opérations et validez ou annulez la transaction manuellement.

## Gestion des transactions par conteneur: 
    Vous utilisez un conteneur de gestion des transactions (comme Spring) qui gère automatiquement les transactions pour vous.

    *@Transactional: Indique qu'une méthode ou une classe doit s'exécuter dans le cadre d'une transaction.
    
    *@Propagation: Détermine le comportement de propagation de la transaction.
    
    *@Isolation: Détermine le niveau d'isolation de la transaction.
    
    *@ReadOnly: Indique si la transaction est en lecture seule.
    
    *@RollbackFor: Spécifie les exceptions qui doivent entraîner une annulation de la transaction.


## @Transactional:
Lorsqu'une méthode annotée avec @Transactional est appelée, Spring va automatiquement gérer le début, la fin et la validation (commit ou rollback) de la transaction. <b>Si une exception est levée au cours de l'exécution de la méthode, Spring annulera la transaction (rollback) pour garantir la cohérence des données</b>.