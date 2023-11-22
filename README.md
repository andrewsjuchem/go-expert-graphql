# Go Expert - GraphQL

How to run the server
```
go run cmd/server/server.go
```

Accessing the server (GraphQL Playground)
- URL: http://localhost:8080/
- <details open>
  <summary>Playground commands</summary>
```
mutation createCategory {
	createCategory(input: {name: "Technology", description: "Technology Course"}) {
		id
		name
		description
	}
}

mutation createCourse {
	createCourse(input: {name: "Technology", description: "Technology Course", categoryId: "ed0c900c-7c0e-450d-9564-689c6117096a"}) {
		id
		name
		description
	}
}

query queryCategories {
	categories {
		id
		name
		description
	}
}

query queryCategoriesWithCourses {
	categories {
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

query queryCourses {
	courses {
		id
		name
		description
	}
}

query queryCoursesWithCategory {
	courses {
		id
		name
		description
    category {
      id
      name
      description
    }
	}
}
```
</details>

Generating GraphQL template project using "gqlgen".
```
go run github.com/99designs/gqlgen init
go mod tidy
go run github.com/99designs/gqlgen generate
```

