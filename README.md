# Imaginify - SAAS for AI Stock Photo Manipulation
Web app that simulates a stock photo database for users. 
Users can log in to the application and perform transformations to images leveraging the power of **AI**. 
Users can also upload, delete and update photos.
## Functionalities and implementation
### Browsing
Users can browse through the photos uploaded by themselves and other users.
All data for photos is stored in a **mongoDB** collection (MongoDB Atlas).
![Home](/public/demo/home/home1.png)
The images are displayed using pagination to improve performance.
There is also a search bar which can be used to search for specific images through the title, or using AI powered search to search using keywords.
Note how the titles of the showed images do not include the word 'sky'.
![Home](/public/demo/home/home2.png)
Pagination and query variables are implemented through search bar params.
### Log in and sign up
User authentication as a whole is implemented utilizing **Clerk**.
Clerk protects all routes configured.
![Login](/public/demo/login/login1.png)
User information is synchronized with our database user data stored in MongoDB Atlas.
We do this using **webhooks** and API endpoints.
![Login](/public/demo/login/login2.png)
### Transformations
Users can perform transformations to images using AI. 
For this, we use **Cloudinary's API**.
Users can then download images, or upload them to the database, so other users can see them.
The transformation form is implemented using **Zod**.
We can perform several different transformations to images.
![Transformations](/public/demo/transformations/imgUpload.png)
#### Image restore
![Transformations](/public/demo/transformations/imgRestore.png)
#### Generative fill
![Transformations](/public/demo/transformations/imgFill.png)
#### Object remove
![Transformations](/public/demo/transformations/imgRemove.png)
#### Object recolour
![Transformations](/public/demo/transformations/imgRecolour.png)
#### Background remove
![Transformations](/public/demo/transformations/imgBgRemove.png)
### Profile view
Users can review their own image transformations updated.
![Profile](/public/demo/profile/profile1.png)
They can select specific images to perform mutations such as updating the images or deleting them.
![Profile](/public/demo/profile/profile2.png)
### Credits
The SAAS implements a credit based system with **stripe** and **webhooks**.
![Credits](/public/demo/credits/credits1.png)
Users can purchase credits to be able to transform images.
![Credits](/public/demo/credits/credits2.png)
