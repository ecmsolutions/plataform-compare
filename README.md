# Plataform Compare

## Features

|                    | Github (SaaS)     | GitLab (SaaS) | GitLab (Self-hosted) | Current     |
|--------------------|-------------------|---------------|----------------------|-------------|
| SCM                | Git               | Git           | Git                  | SVN         |
| CI/CD              | Actions           | CI/CD         | ---                  | Jenkins     |
| Binary Repository  | Packages          | Package       | ---                  | Artifactory |
| Image Registry     | Packages          | Registry      | ---                  | ---         |
| Project Management | Projects / Issues | Plan / Issues | Plan / Issues        | Mantis      |
| [Wiki](#diagrams)  | Wiki              | Wiki          | Wiki                 | ---         |

## Restrictions

|                      | Github (SaaS) | GitLab (SaaS) | GitLab (Self-hosted) | Current |
|----------------------|---------------|---------------|----------------------|---------|
| Private repositories | Unlimited     | Unlimited     | Unlimited            | ---     |
| Users                | Unlimited     | 5 users/group | Unlimited            | ---     |
| Runners              | ---           | 400 min/month | ---                  | Jenkins |

## SCM

 - GitLab

![gitlab-scm](assets/gitlab-scm.jpg)

 - Github

![github-scm](assets/github-scm.jpg)

## CI/CD

 - GitLab

 - Github

## Binary Repository

 - GitLab

 - Github

## Wiki

### Diagrams

#### ER

```mermaid
---
title: Orders Model
---
erDiagram
    CUSTOMER ||--o{ ORDER : places
    CUSTOMER {
        string name
        string custNumber
        string sector
    }
    ORDER ||--|{ LINE-ITEM : contains
    ORDER {
        int orderNumber
        string deliveryAddress
    }
    LINE-ITEM {
        string productCode
        int quantity
        float pricePerUnit
    }
```

#### Sequence

```mermaid
sequenceDiagram
    Frontend->>Apigateway: GET /o
    Apigateway->>Orders: GET /orders
    Orders->>MongoDB: find()
    MongoDB-->>Frontend: orders found
```

