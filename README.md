# MyCompany

A short live coding test for intermediate .NET developers. 
The duration should not exceed 45 min.

# Objectives

The goal of this application is to create a small REST API that allow to:

- create a client
- create a command for a client
- get all the commands from a client


# Models

Here are the models that must be used : 

```csharp

public class Client
{
    public Guid Id { get; set; }
    public string Nom { get; set; }
    public string Email { get; set; }
}

public class Commande
{
    public Guid Id { get; set; }
    public Guid ClientId { get; set; }
    public DateTime Date { get; set; }
    public List<LigneCommande> Lignes { get; set; }
}

public class LigneCommande
{
    public string Produit { get; set; }
    public int Quantite { get; set; }
}

```

# Tasks

The candidate must create the following endpoints:

- POST /clients ? Create a client.
- POST /clients/{id}/commands ? Create a command for a client
- GET /clients/{id}/commands ? Return the client command

The candidate must used:

- InMemory database
- DTOs (ex. CreateClientRequest, CreateCommandeRequest).
- DI 
- Async



# Bonus

Add a method in the command service that calculate the total amount for a list of command.
Use TDD with xunit to test the limit cases.



