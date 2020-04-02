# graphql-postgres-docker

GraphQL, PostgreSQL, Docker, Prisma, Nexus, Apollo

-   Prisma as your data modeling tool  
    Prisma was used, see prisma folder here: https://github.com/skaduusch/graphql-postgres-docker/tree/master/prisma

-   Docker-based PostgreSQL, MySQL, or MongoDB as your data store  
    To launch docker with a PostgreSQL database run:

```
npm run launchDocker
```

-   At least 3 Query resolvers to get data from your server  
    See queries here: https://github.com/skaduusch/graphql-postgres-docker/blob/master/src/query.js

-   At least 2 Mutation resolvers allowing users to create, update, or upsert an item.
-   At least 1 Mutation resolver allowing users to delete an item.  
    See mutations here: https://github.com/skaduusch/graphql-postgres-docker/blob/master/src/mutation.js

-   Your datastore will contain at least 25 items  
    Items populated from this json file: https://github.com/skaduusch/graphql-postgres-docker/blob/master/prisma/data/wake-products.json

-   Your app will be deployable locally using Docker and will have seed data entered into the datastore.

## To deploy the server once downloading the code base run the following npm scripts:

```
npm install
npm run launchDocker
npm run createDB
npm run generate
npm run seed
```

You can then launch the Prisma Studio to view the information in the database with:

```
npm run dev
```

Or you can experiment with making queries in the Apollo server by running:

```
npm start
```

<details>
<summary>See Query Samples</summary>

```
query allProducts {
	Products {
		id
		name
		category
		description
		price
		imageUrl
	}
}
```

```
query singleProduct {
	Product(id: "ck8atgsrx0007kr7b3w3azya1") {
		id
		name
		category
		description
		price
		imageUrl
	}
}

```

```
query productCategory {
	Category(category: "Wakeboards") {
		id
		name
		category
		description
		price
		imageUrl
	}
}
```

```
mutation addProduct {
	createProduct(
		name: "Hyperlite Riot Nova"
		category: "Wakeboards"
		description: "This is the Riot Nova, it's sick."
		price: 799
		imageUrl: "https://www.hyperlite.com/images/square.png"
	) {
		id
		name
		category
		description
		price
		imageUrl
	}
}
```

```
mutation updateProduct {
	updateProduct(
		id: "ck8ckndoo0000kb7bi8gdw2li"
		description: "This is teh best wakeboard in existence. Ever. Don't even argue."
	) {
		id
		name
		category
		description
		price
		imageUrl
	}
}
```

```
mutation deleteProduct {
	deleteOneProduct(where: { id: "ck8gw1hpu0000lr7biier71xy" }) {
		id
		name
		category
	}
}
```

</details><br>

-   All of your source code will be properly uploaded to GitHub :octocat:  
    See here: https://github.com/skaduusch/graphql-postgres-docker

-   Your ReadMe file will accurately describe your server install and run process and how to use the APIs

*   [x] You're looking at it. :metal:
