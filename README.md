Alright, so let's build something. 

This repository is an effort for me to learn about building "modern" apps using tools like Docker, .NET Core, ElasticSearch, etc., using "modern" architectures, such as micro-services, and using modern dev-ops practice, such as continuous integration and deployment. 

## What is the App?

So my wife brought up to me the idea of a sort of "Reverse Cookbook", where she could a list of reciples for different dinners she could make based off of the different things in the kitchen. Needless to say, this sounded like a pretty cool idea for an app! 

Let's break down a few of the different components that makes sense for an app like this:
- We need to keep track of what ingredients a given user has. In order for the app to compile a list of recipes, it needs to know what ingredients are at the user's disposal. For each user, we need to provide them a way to let app know that they have 4 sticks of butter, for example. 
    - This example, "4 sticks of butter", implies an "ingredient" (butter), a "unit" (sticks), and a "quantity" (4). Things to keep in mind. 
- We need a list of recipes. Each user can submit their own recipes, which then other users can use to access. 
    - A recipe is kind of a complex thing, at it's simplest form, a recipe consists of ingredients and steps. 
- We need to be able to search through these recipes to provide the user with some dinner options based off of what ingredients they have. 

## What tools do you have in mind?

Based off of the requirements listed above, these are the current pieces of the puzzle:
1. Front-end Web (SPA Application)
- ExpressJS hosting ReactJS frontend
2. Front-end Native Mobile 
- Xamarin.Forms
3. Recipe Storage Service (kind of CRUD operations for recipes)
- Node.JS with MongoDB
4. Recipe Community Service (for allowing users to review and comment on recipes)
- ASP.NET Core with Postgres
5. Pantry Service (for storing the ingredients that a user currently has)
- Giraffe (F#) with <DATABASE>
6. Search Service (for retreiving a list of recipes based on the user's Pantry) 
- <Framework> with ElasticSearch 