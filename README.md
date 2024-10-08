# biblioteca-online
Projeto para digitalizar biblioteca municipal com a finalidade de melhorar a experiencia dos leitores de patrocinio e estimular a leitura.

## Descrição

  Idéia deste protejo é possibilitar a melhora do acesso aos livros disponíveis na biblioteca municipal aos cidadãos do município. Por meio de consultas de disponibilidade e reservas online, a população poderia, de casa, garantir sua leitura da semana. 

## O projeto possui integração com swagger para consumo devido de seus Endpoints.

URL do documento Swagger: http://localhost:8080/swagger-ui/index.html

<img src="./images/swagger.png" alt="Texto alternativo" width="720"/>


## UML do Projeto

```mermaid

classDiagram
    class User {
        +Long id
        +String name
        +String email
        +String password
        +List~Reservation~ reservations
        +String document
        +String cep
    }
    
    class Reservation {
        +Long id
        +User user
        +Book book
        +LocalDate reservationDate
        +LocalDate dueDate
        +boolean isReturned
    }
    
    class Book {
        +Long id
        +boolean disponibilidade
        +String title
        +String author
        +String isbn
        +String publisher
        +int publicationYear
        +String genre
        +int quantityAvailable
        +int numberOfPages
        +String language
        +String resume
        +String bookCover
        +List~String~ tags
    }

    User "1" --> "0..*" Reservation : has
    Reservation "1" --> "1" Book : reserves
```
