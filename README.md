# ORM-E-Commerce-Back-End
Object-Relational Mapping (ORM): E-Commerce Back End


# ORM Challenge: E-Commerce Back End (Week 13 Challenge)

## Summary of Task

This week my task was to build the back end for an e-commerce site by modifying starter code. I configured a working Express.js API to use Sequelize to interact with a PostgreSQL database.

Because this application is not deployed, I have provided a link to a walkthrough video at the end of this README that demonstrates its functionality and passes all of the tests. 

Below are the following Challenge requirements according to the 
**User Story** & **Acceptance Criteria**

## User Story

```md
AS A manager at an internet retail company
I WANT a back end for my e-commerce website that uses the latest technologies
SO THAT my company can compete with other e-commerce companies
```

## Acceptance Criteria

```md
GIVEN a functional Express.js API
WHEN I add my database name, PostgreSQL username, and PostgreSQL password to an environment variable file
THEN I am able to connect to a database using Sequelize
WHEN I enter schema and seed commands
THEN a development database is created and is seeded with test data
WHEN I enter the command to invoke the application
THEN my server is started and the Sequelize models are synced to the PostgreSQL database
WHEN I open API GET routes in Insomnia for categories, products, or tags
THEN the data for each of these routes is displayed in a formatted JSON
WHEN I test API POST, PUT, and DELETE routes in Insomnia
THEN I am able to successfully create, update, and delete data in my database
```


## Additional Requirements

My application uses the [pg](https://node-postgres.com/) and [Sequelize](https://www.npmjs.com/package/sequelize) packages to connect my Express.js API to a PostgreSQL database and the [dotenv](https://www.npmjs.com/package/dotenv) package to use environment variables to store sensitive data.


I use the `schema.sql` file in the `db` folder to create the database with PostgreSQL shell commands. 

### Database Models

My database contains the following four models, including the requirements listed for each model:

* `Category`

  * `id`

    * Integer.
  
    * Doesn't allow null values.
  
    * Set as primary key.
  
    * Uses auto increment.

  * `category_name`
  
    * String.
  
    * Doesn't allow null values.

* `Product`

  * `id`
  
    * Integer.
  
    * Doesn't allow null values.
  
    * Set as primary key.
  
    * Uses auto increment.

  * `product_name`
  
    * String.
  
    * Doesn't allow null values.

  * `price`
  
    * Decimal.
  
    * Doesn't allow null values.
  
    * Validates that the value is a decimal.

  * `stock`
  
    * Integer.
  
    * Doesn't allow null values.
  
    * Set a default value of `10`.
  
    * Validates that the value is numeric.

  * `category_id`
  
    * Integer.
  
    * References the `Category` model's `id`.

* `Tag`

  * `id`
  
    * Integer.
  
    * Doesn't allow null values.
  
    * Set as primary key.
  
    * Uses auto increment.

  * `tag_name`
  
    * String.

* `ProductTag`

  * `id`

    * Integer.

    * Doesn't allow null values.

    * Set as primary key.

    * Uses auto increment.

  * `product_id`

    * Integer.

    * References the `Product` model's `id`.

  * `tag_id`

    * Integer.

    * References the `Tag` model's `id`.



### Associations

I executed association methods on the Sequelize models to create the following relationships between them:

* `Product` belongs to `Category`, and `Category` has many `Product` models, as a category can have multiple products but a product can only belong to one category.

* `Product` belongs to many `Tag` models, and `Tag` belongs to many `Product` models. Products may have multiple tags and tags to have many products by using the `ProductTag` through model.


### API Routes to Perform RESTful CRUD Operations

I filled out the unfinished routes in `product-routes.js`, `tag-routes.js`, and `category-routes.js` to perform create, read, update, and delete operations using Sequelize models.


### Seeding the Database

After creating the models and routes, I can run `npm run seed` to seed data to the database so that I can test my routes.

### Sync Sequelize to the Database on Server Start

I also created the code needed in `server.js` to sync the Sequelize models to the PostgreSQL database on server start.


## Project View

![ORM E-Commerce App View](<Assets/images/ORM E-Commerce App View.jpg>)

## Contact Information
Thanks for visiting!

If you would like to learn more, or contact me, feel free to reach me at the following:

<ul>
    <li>Video Walkthrough URL: https://drive.google.com/file/d/1MDFLneHJecgw75_ZbxERSDcnRiIgxvUq/view </li>
    <li>GitHub URL: https://github.com/mandrade09/-ORM-E-Commerce-Back-End </li>
    <li>E-mail: mattandrade09@gmail.com </li>
    <li>Phone: 310.903.9150</li>
</ul>

<p>
<footer> &ndash; Matthew Andrade</footer>
</p>