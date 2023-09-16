# GraphQL API in Go

Welcome to our GraphQL API in Go! This application provides resources to access information about courses and categories. This documentation will guide you through the core aspects of the API, including the types of queries you can make and how to contribute to the project.

## Project Motivation

This project is part of my ongoing journey to enhance my knowledge in Go programming and application architecture. It's based on a course I'm currently taking, with the primary goal of improving my skills to create the best possible applications. I believe that continuous learning and hands-on experience are key to becoming a proficient developer.

By working on this project, I aim to:

- Gain a deeper understanding of Go programming.
- Explore best practices in building scalable and maintainable applications.
- Apply GraphQL for efficient data querying.
- Learn about structuring APIs using a category-course model.
- Collaborate with the open-source community to contribute and improve this project further.

Feel free to join me on this journey, and let's create amazing applications together!

## Queries

The GraphQL API offers a variety of queries to retrieve information about courses and categories. Here are some example queries:

### Fetching a list of courses:

```graphql
query {
  courses {
    id
    name
    description
    category {
      name
    }
  }
}
```

### Getting details of a specific course:
```graphql
query {
  course(id: 1) {
    name
    category {
      name
    }
  }
}
```

### Filtering courses by category:
```graphql
query {
  coursesByCategory(categoryId: "9f788f52-7a20-4973-aca8-bdaccea7d6ee") {
    id
    name
    description
    courses {
      id
      name
      description
    }
  }
}
```

### Retrieving a list of categories:
```graphql
query {
  categories {
    id
    name
    courses {
      id
      name
      description
    }
  }
}
```

### Getting details of a specific category:
```graphql
query {
  categories(id: 1) {
    name
    courses {
      id
      name
      description
    }
  }
}
```

### Adding a new course:
```graphql
mutation {
  createCourse(
    name: "New Course"
    description: "Description of New Course"
    category: "Technology"
  ) {
    id
    name
  }
}
```

