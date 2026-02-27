hello
# Blog BackEnd API - Project Overview

## Project Goal

Create a backend for Blog Application:

- Support full CRUD operations
- All users to create account and login
- Deploy to Azure
- Uses SCRUM workflow concepts
- Introduces Azure DevOps practices

## Stack

    - Back end will be in .Net 9, ASP.NET Core, EF Core, SQL Server.
    - Front End will be done in Next JS with TypeScript (To be done by. Jacob) flowbite(tailwind). Deploy with TBA (Vercel or Azure)

## Application Features

### User Capabilities

- Create an account
- Login
- Delete acoount

### Blog Features 
 
 - View all published blog posts
 - Filter blog posts
 - Create new posts
 - Edit existing posts
 - Delete posts
 - Publish/ Unpublish posts

 ### Pages (Frontedn Connected to API)

 - Create Account Page
 - Blog view post page of plished items
 - Dashboard page ( this is the profile page will edit, delete, and publish and unpublish our blog posts)
 
 - **Blog Page**
    - Display all published blog items

- **Dashboard**
    - User profile page
    - Create blog posts
    - Edit blog posts
    - Delete blog posts

## Project Folder Structure
 
### Controllers

#### UserController

Handles all users interaction.

Endpoints:

- Login
- Add user
- Update Users
- Delete User

#### BlogController

Handles all blog operations.

Endpoints: 

- Create Blog Item (C)
- Get All Blog Items (R)
- Get Blog Items By Category (R)
- Get Blog Items by Tags (R)
- Get Blog Items by Date (R)
- Get Published Blog Items (R)
- Update Blog Items (U)
- Delete Blog Item (D)
- Get Blog Items by UserId

> Delete will be use for soft delete / publish logic

---

## Models

### UserModel

```csharp

int Id
string Username
string Salt
string Hash  

### BlogItemModel

int Id
int UserId
string PublisherName
string Title
string Image
string Description
string Date
string Category
string Tags
bool IsPublished
bool IsDeleted

## Items Saved to our DB
### We need a way to sign in with our user name and password

```csharp

### LoginModel

    string Username
    string Password

### CreateAccountModel
    int Id = 0
    string Username
    string Password

### PasswordModel

    string Salt
    string Hash

```

### Services
    Context/Folder
    - DataContext
    - UserService/file
        - GetUserByUsername
        - Login
        - AddUser
        - UpdateUser
        - DeleteUser
### BlogItemService
    - AddBlogitems
    - GetAllBlogItems
    - GetBlogItemsByCategory
    - GetBlogItemsByTags
    - GetBlogItemsByDate
    - GetPublishedBlogItems
    - UpdateBlogItems
    - DeleteBlogItems
    - GetUserById
### PasswordService

    - Hash Password
    - Very Hash Password