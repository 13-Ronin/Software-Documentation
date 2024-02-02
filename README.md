This is the documentation of the software part of the graduation project. The team consists of 4 developers specializing in specific fields (tracks).

- Mohamed Yousef and Mohamed Samir in the frontend development
- Mohamed Hamid in the backend development
- Mohamed Ashraf in the mobile app development

---

# How we manage the development process

One of the key points that we need in the team is the well-organized and easy-to-access information. We need to be tidy, so we should use a special type of app for messaging and chatting like Slack and Discord. Emails are professional but are more useful for important information and between different teams, it is not suitable for daily communication between the team members. We used **Discord** which enables us to create multiple categories for each sub-team, and for each of the categories we can create channels for each part of the software, backend, frontend, and mobile app development.

To organize our documents including this one, we used **Notion** which provides a good way to create page embed resources like links and files in the document. Notion also has a very powerful feature, databases.

One of the documents here is the requirements document where we write the features and the requirements of the system and the additional features which we may work on. We could’ve used Notion to manage tasks and sprints (or cycles) as well it is a bit harder for us to create the databases of tasks and link them together. When powerful and feature-rich apps like Jira and Linear exist it is not a wise decision to build the process here in notion.

We chose **Linear**, the relatively new app which is gaining more user base and popularity in the software industry. It doesn’t only provide a way to add tasks (also called issues) and assign them to users. It provides a way to set a roadmap for the team and split the project into multiple smaller projects. Linear also has another feature that is crucial for our team, cycles. Our cycle is 1 week where we plan, develop, and test the tasks, and during the cycle, we review our progress and plan for the next cycle. This way, we keep our work organized and efficient.

List of apps and services used:

1. **Notion**: documents and resources management.
2. **Google Drive**: documents and resources management.
3. **Linear**: tasks, weekly plans, and roadmaps.
4. **GitHub**: services to manage git repositories and CI/CD processes.
5. **Discord**: chatting and communication.
6. **Figma**: prototyping and designing UI/UX.
7. **VSCode**: development and writing code.

# UI/UX

- Ideas to talk about
    - Why UI/UX is important
    - Choosing the design system and components library
    - Why do you build components in Figma?
    - The thinking process while designing a page
        - افهم المطلوب
        - اكتب تفاصيل كل صفحة وأقسامها
        - شخبط على ورق **وانظر لأمثلة وإلهامات**
        - نفذ وبطل أفورة
    

# Frontend architecture

- Didn’t Documented Yet
    - Testing ⇒ Cypress & Jest & React Query Axios
    - SEO
    - Accessibility
    - Performance

# Backend architecture

## **Overview**
    
The backend architecture of the pharmacy website is designed to provide a robust and scalable platform for managing pharmaceutical data and serving endpoints to support the frontend application and mobile application. Built on Django Rest Framework (DRF), the architecture follows best practices to ensure security, performance, and maintainability.
    
## **Components**
    
### **1. Django Framework**
        
Django provides the foundation for the backend application, offering a high-level Python web framework for rapid development and clean, pragmatic design. It handles routing, request handling, authentication, and database interactions.
        
### **2. Django Rest Framework (DRF)**
        
DRF extends Django's capabilities to support building Web APIs. It provides serializers, views, and generic API views to streamline the creation of RESTful endpoints. DRF also offers authentication, permissions, and throttling mechanisms out of the box.
        
### **3. Database Layer**
        
 The backend relies on a relational database management system (RDBMS) to store and retrieve pharmaceutical data. Common choices include PostgreSQL, MySQL, or SQLite
        
 we use SQLite for development and PostgreSQL for production.
### **4. Models**
        
 Django's ORM (Object-Relational Mapping) is used to define models representing pharmaceutical entities such as drugs, prescriptions, users, and orders. These models map to database tables, allowing for easy manipulation and querying of data.
        
###  **5. Views**
        
 DRF views handle incoming HTTP requests and generate appropriate responses. Views are responsible for processing data, validating inputs, and interacting with the database through Django models. Views may be class-based or function-based, depending on the complexity of the logic.
        
### **6. Serializers**
        
 Serializers in DRF convert complex data types such as Django models into native Python data types suitable for rendering into JSON or other content types. They facilitate data validation, parsing incoming request data, and formatting outgoing response data.
### **7. Middleware**
        
 Middleware components in Django intercept HTTP requests and responses, allowing for cross-cutting concerns such as logging, security, or custom preprocessing logic. Middleware can be used to enforce CORS policies, handle exceptions, or modify request/response headers.
        
### **8. Testing**
        
 Unit tests, integration tests, and end-to-end tests ensure the reliability and correctness of the backend application. Django provides robust testing frameworks, and tools like pytest can be used for comprehensive test coverage.
        
### **9. Deployment and Scalability** 
  The backend application can be deployed on cloud platforms like AWS, Azure, or Google Cloud Platform for scalability and high availability. Containerization with Docker and orchestration with Kubernetes simplify deployment and management of the application across different environments.we used pythonanywhere because it free	The backend application can be deployed on cloud platforms like AWS, Azure, or Google Cloud Platform for scalability and high availability. Containerization with Docker and orchestration with Kubernetes simplify tdeployment and management of the application across different environments.

# Mobile architecture

# Authentication

    
## backend
### overview    
DRF provides built-in support for various authentication mechanisms, including token-based authentication, session authentication, OAuth, etc. Authentication ensures that only authorized users can access protected endpoints. Authorization mechanisms control what actions users can perform based on their roles and permissions.
### list of used library.
    
#### **1. Django Allauth**
    
 **Purpose**: Django Allauth is a flexible authentication solution for Django applications, offering support for social account authentication like Goggle and Facebook, email verification, and account management.
    
#### **2. Dj-Rest-Auth**
    
 **Purpose**: Dj-Rest-Auth extends Django Allauth's functionality to provide RESTful endpoints for user authentication and registration.
    
#### **3. Simple JWT (JSON Web Tokens)**
    
 **Purpose**: Simple JWT is a lightweight library for creating and validating JSON Web Tokens (JWT) to implement token-based authentication in DRF and provide access and refresh tokens and can set period for them

# Profile page and settings
## frontend
........
## backend
    
### **Overview**
        
 User profiles play a crucial role in providing a personalized experience for users within our application. They allow users to manage their information, preferences, and settings. Profile includes personal details, contact information, preferences, and any other relevant data that enhances the user experience.
        
### **Components**
        
#### **1. Profile Model**
            
 The profile model stores additional user information. This model typically extends Django's built-in **`User`** model or links to it using a one-to-one relationship.
            
 Example:
            
 ```python
            
            from django.contrib.auth.models import User
            class Profile(models.Model):
                user = models.OneToOneField(User, on_delete=models.CASCADE)
                image= models.ImageField(upload_to='avatars/', blank=True)
                # more fields 
            
 ```
            
#### **2. Profile Serializers**
            
Forms or serializers are used to validate and process profile data when users update their profiles through forms or API endpoints.
            
#### **3. Profile Views or Endpoints**
            
Views or endpoints handle profile-related requests, such as displaying profile information, updating profiles, or deleting profiles.
            
### **Functionality**
        
#### **1. Profile Creation**
        
Profiles automatically created upon user registration
        
#### **2. Profile Update**
        
 Users should have the ability to update their profile information
        
#### **3. Profile Retrieval**
        
 Users should be able to view their own profiles

 #### **4. Profile Picture Management**
        
 Users should be able to upload, update, or remove profile pictures
        
#### **5. Profile Privacy Settings**
        
 Users should have control over the visibility of their profile information. They may choose to make their profiles public, private, or visible to specific users or groups.
        
#### **6. Profile Deletion**
        
 Users is able to delete their profiles.
                
#### **Access Control**
        
Access to profile information is restricted based on user permissions.
        

# Home page
## frontend
## backend
    
### Overview
    
 The home page serves as the entry point to our application, providing users with essential information, navigation options, and access to key features. Product management encompasses the creation, display, and manipulation of products within our application, including adding new products, updating existing ones, and presenting them to users.
    
### Components
    
#### 1. Home page
    
The home page typically consists of the following components:
    
 **Header**: Contains branding elements, navigation links, and user authentication options.
    - **Hero Section**: Showcases featured products, promotions, or announcements to capture user attention.
    - **Product Categories**: Displays a list of product categories or featured collections to help users discover products.
    - **Latest Products**: Highlights recently added or popular products to encourage exploration.
    - **Footer**: Includes additional navigation links, contact information, and social media links.
    
#### 2. Product Management
    
 Product management involves the following components:
    
 **Product Model**: Defines the structure of product data, including attributes such as name, description, price, and image.
    - **Product CRUD (Create, Read, Update, Delete) Operations**: Enables administrators to add, edit, and remove products from the system.
    - **Product Listing**: Presents products to users in a visually appealing and informative manner, allowing them to browse and search for products.
    - **Product Detail Page**: Provides detailed information about individual products, including images, descriptions, specifications, and pricing.
    - **Product Categories and Tags**: Organizes products into categories and tags to facilitate navigation and filtering.
    
### Functionality
    
#### 1. Home Page Features
    
 **Featured Products**: Highlight selected products on the home page to attract user attention.
    - **Promotions and Announcements**: Display promotional offers, discounts, or announcements to engage users.
    - **Navigation Links**: Provide clear and intuitive navigation links to guide users to different sections of the application.
    - **Search Functionality**: Allow users to search for products directly from the home page for quick access.
    
#### 2. Product Management Features
    
**Product Creation**: Enable administrators to add new products to the system, including specifying product details and uploading images.
    - **Product Editing**: Allow administrators to modify existing product information, such as updating descriptions or adjusting pricing.
    - **Product Deletion**: Provide the ability to remove products from the system when they are no longer available.
    - **Product Listing and Pagination**: Display products in paginated lists to improve performance and user experience.
    - **Product Filtering and Sorting**: Implement filters and sorting options to help users find products based on criteria such as category, price, or popularity.
    
### Security Considerations
    
**Access Control**: Ensure that only authorized users, such as administrators, can access product management functionalities.
    - **Data Validation**: Validate product data to prevent errors and ensure consistency in the database.
    - **Image Upload Security**: Implement measures to secure image uploads, such as file type validation and size limits, to prevent malicious uploads.

# Cart of products

# Payment process

# Map
