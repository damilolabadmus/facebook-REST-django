# facebook-REST-django

# facebook-clone

    --> Requirement Gathering
## Functional
- Users can post
- Users can share, like, comment, delete, update post
- Users can add and remove friends
- Users can change post access to public/private
- Users can see news feeds
- Users can search for friends
- Users can share profile
- Users can delete account

## Non functional
- Application should be secure
- The application should be available

## Database Design
- POST
    - id, bigint, autoincrement, primary
    - text: text
    - author: USER
    - created_on: datetime
    - updated_on: datetime
    
- POST_MEDIA
    - id: bigint
    - file: varchar(url)
    - post: POST
    
- USER
    - id, bigint, autoincrement, primary
    - username: varchat(20)
    - email: varchar(120)


- PROFILE
    - id, bigint, autoincrement, primary
    - owner: USER
    - image: varchar(url)
    - address: ADDRESS
    - created_on: datetime
    - updated_on: datetime
    
- ADDRESS
    - id, bigint, autoincrement, primary
    - zip_code
    - country
    - created_on: datetime
    - updated_on: datetime   
    
- COMMENT
    - id, bigint, autoincrement, primary
    - text: text
    - author: USER
    - created_on: datetime
    - updated_on: datetime
    
- LIKE
    - id, bigint, autoincrement, primary
    - post: POST
    - owner: USER
    - created_on: datetime
    - updated_on: datetime
    
- FRIEND
    - id, bigint, autoincrement, primary
    - friended: USER
    - created_on: datetime
    - updated_on: datetime

## API Design
- [GET, POST, PUT, PATCH, DELETE]
- [GET_LIST, GET_ONE, CREATE, UPDATE_ALL, UPDATE_SOME, DESTROY]
- Models- POSTS, COMMENTS, LIKES, FRIENDS

## Structure
-POSTS
    - POST
    - POST_MEDIA
    - COMMENT
    - LIKE
- USERS
    - User
    - Friend
    - Profile
------>
- POST
    - GET_LIST: returns a list of posts
        - URL: /api/v1/posts
        - METHODS: GET
        - REQUEST:
             - HEADERS: Authorization
             - BODY: 
        - RESPONSE:
            - HEADER: Authorization
            - BODY: [
                {
                    id: int,
                    text: Str,
                    created_on: datetime,
                    author: User,
                }
            ]   
            
      --> Design
       Structure of data
       Size of data
       Type of database
       Setup of database (devops work) 
       
            API Design
           ------------