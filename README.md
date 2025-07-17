# MyCompany

A short live coding test for intermediate .NET developers.  
The expected duration is around **45 minutes**.

# Objectives

The goal is to create a small REST API that allows you to:

- Create a client
- Create a command for a client
- Retrieve all commands of a client


# Models

The following models **must be used**: 

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

You must implement the following endpoints:

- POST /clients ? Create a client
- POST /clients/{id}/commands ? Create a command for a specific client
- GET /clients/{id}/commands ? Return all commands for a specific client

You are expected to:

- Use an in-memory database (just a List<T>)
- Use DTOs for input (e.g. CreateClientRequest, CreateCommandeRequest)
- Apply Dependency Injection
- Use async/await, even if it seems unnecessary for in-memory storage

# Bonus

Add a method in your command service to calculate the total amount for a given list of commands.

Use TDD with xUnit to test edge cases, such as:

- Empty command list
- Products with zero quantity
- Multiple products with various prices



