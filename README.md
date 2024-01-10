# Plataform Compare

## Features

|                                           | Github (SaaS)     | GitLab (SaaS) | GitLab (Self-hosted) | Current     |
|-------------------------------------------|-------------------|---------------|----------------------|-------------|
| [SCM](#scm)                               | Git               | Git           | Git                  | SVN         |
| [CI/CD](#ci_cd)                           | Actions           | CI/CD         | ---                  | Jenkins     |
| [Binary Repository](#binary_repository)   | Packages          | Package       | ---                  | Artifactory |
| [Image Registry](#image_registry)         | Packages          | Registry      | ---                  | ---         |
| [Project Management](#project_management) | Projects / Issues | Plan / Issues | Plan / Issues        | Mantis      |
| [Wiki](#diagrams)                         | Wiki              | Wiki          | Wiki                 | ---         |

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

![gitlab-cicd](assets/gitlab-cicd.jpg)

 - Github

![github-cicd](assets/github-cicd.jpg)

## Binary Repository

 - GitLab

![gitlab-bin-repo](assets/gitlab-bin-repo.jpg)

 - Github

![github-bin-repo](assets/github-bin-repo.jpg)

## Image Registry

- GitLab

![gitlab-registry](assets/gitlab-registry.jpg)

- Github

![github-registry](assets/github-registry.jpg)

## Project Management

- GitLab

![gitlab-project-mgnt](assets/gitlab-project-mgnt.jpg)

- Github

![github-project-mgnt](assets/github-project-mgnt.jpg)

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

