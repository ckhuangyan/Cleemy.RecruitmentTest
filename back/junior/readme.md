# Cleemy : test technique back (junior)

Le test consiste à réaliser une application web en .NET Core avec une API pour :
 - Créer des dépenses
 - Lister les dépenses

## Qu'est-ce qu'une dépense ?

Une dépense est caractérisée par :
 - Un utilisateur (personne qui a effectué l'achat)
 - Une date
 - Une nature (valeurs possibles : `Restaurant`, `Hotel` et `Misc`)
 - Un montant et une devise
 - Un commentaire

Un utilisateur est caractérisé par :
 - Un nom de famille
 - Un prénom
 - Une devise dans laquelle il effectue ses achats

## Création d'une dépense

Avant de persister la dépense, il faut vérifier qu'elle soit valide.

Règles de validation d'une dépense :
 - Une dépense ne peut pas avoir une date dans le futur,
 - Une dépense ne peut pas être datée de plus de 3 mois,
 - Le commentaire est obligatoire,
 - Un utilisateur ne peut pas déclarer deux fois la même dépense (même date et même montant),
 - La devise de la dépense doit être identique à celle de l'utilisateur.

## Liste des dépenses

L'API doit permettre de :
 - Lister les dépenses pour un utilisateur donné,
 - Trier les dépenses par montant ou par date,
 - Afficher toutes les propriétés de la dépense ; l'utilisateur de la dépense doit apparaitre sous la forme `{FirstName} {LastName}` (eg: "Anthony Stark").

## Stockage

Dans un premier temps, on persiste les données en mémoire.

Si tu as le temps et que tu es à l'aise avec Entity Framework, tu peux utiliser SQL Server comme moyen de persistence.

La table des utilisateurs doit être initialisée avec les utilisateurs suivants :
 - Stark Anthony (devise = Dollar américain),
 - Romanova Natasha (devise = Rouble russe).

## Test unitaires

Les règles de validation de la dépense doivent être testées unitairement.

## Notes

 - Pas besoin d'authentification,
 - Aucune interface utilisateur requise.

## Critères d'évaluation

Tu seras notamment évalué sur des critères de maintenabilité de ton code, comme la lisibilité et l'homogénéité.

Le but est que nous puissions facilement comprendre ton code sans que tu aies à nous l’expliquer.

Dans un second temps (lors du petit oral), tu seras amené à nous le présenter et nous expliquer les choix que tu as faits.

## Liens utiles

Quelques liens qui peuvent t'aider pour la réalisation de ce test technique :
 - [Create a web API with ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-web-api)
 - [Dependency injection in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection)
 - [Getting Started with EF Core on ASP.NET Core with a New database](https://docs.microsoft.com/en-us/ef/core/get-started/aspnetcore/new-db)
