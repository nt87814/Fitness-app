Social Fitness - README
===

# Social Fitness

## Table of Contents
1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)
2. [Schema](#Schema)

## Overview
### Description
An app for landlords to find tenants and for tenants to search for places to rent. Users can find properties based on preference matching and will be able to contact the property manager.  

### App Evaluation
[Evaluation of your app across the following attributes]
- **Category:** Social/Productivity
- **Mobile:** Push notifications/alerts
- **Story:** Facilitates the processes of finding people with similar preferences
- **Market:** For people who manage several properties.
- **Habit:** Tenants will frequently check for new offers and landlords will check on potential tenant profiles.
- **Scope:** Would be possible to build with less features.

## Product Spec

### 1. User Stories (Required and Optional)
(high level)
**Required Must-have Stories**

* User can log in
* User can create an account
* User can view challenge list
* User can create a new workout
* User can start challenges
* User can view profile page
* User can view workout detail page

**Optional Nice-to-have Stories**
* User can search for workouts
### 2. Screen Archetypes

* Login screen
   * User can login
* Registration screen
   * User can create a new account
 * Workout Stream
   * User can view a stream of challenges
 * Workout Detail 
   * Displays details not in the stream
 * Workout creation
   * User can post a new workout
   * User can upload a description
   * User can upload photos
 * Search
   * User can search by type
 * Profile
   * User can view information about their own account
   * User can view other user's profiles
 * Settings
   * User can edit their account

### 3. Navigation

**Tab Navigation** (Tab to Screen)

* Home Feed
* Post a workout 
* Search
* Profile detail

**Flow Navigation** (Screen to Screen)

* Login Screen
   * Home
* Registration Screen
   * Home
* Home feed
   * Workout detail
* Search
   * Workout detail
   * Other user profile
* Creation Screen
   * Home (after you finish posting the photo)


## Wireframes
[Add picture of your hand sketched wireframes in this section]
<img src="https://i.imgur.com/zPSitOp.jpg"
 width=600>

### [BONUS] Digital Wireframes & Mockups

### [BONUS] Interactive Prototype

## Schema 
### Models

#### Workout

   | Property      | Type     | Description |
   | ------------- | -------- | ------------|
   | id      | String   | unique id for the user post (default field) |
   | author        | Pointer to User| image author |
   | image         | File     | image that user posts |
   | caption       | String   | image caption by author |
   | workout       | String   | workout description |
   | time       | Number   | time of workout (for running, biking)|
   | difficulty_rating | Number   | average rating of workout |
   | likes_count    | Number   | number of likes for the post |
   | created_at     | DateTime | date when post is created (default field) |
   
   #### Challenge
   | Property      | Type     | Description |
   | ------------- | -------- | ------------|
   | id      | String   | unique id for the user post (default field) |
   | owner_id        | Pointer to User| the author sent this to |
   | workout_id  | String   | workout that is being challenged |
   | recipients        | Array of pointers to User| the users the author sent this to |
   | Pointer to User| the author sent this to |
   | deadline     | DateTime | date when post expires |
   | completed     | Boolean | Shows whether the user has completed the challenge in time |

   
   
   #### User

   | Property      | Type     | Description |
   | ------------- | -------- | ------------|
   | id      | String   | unique id for the user post (default field) |  
   | first_name      | String   | User's first name |  
   | last_name      | String   | User's last name |
   | password      | String   | User's password |
   | created_at     | DateTime | date when post is created (default field) |
   | updated_at     | DateTime | date when post is last updated (default field) |
   | friends      | Array of user ids   | List of friends |
   
   
### Networking

   - Home Feed Screen
      - (Read/GET) Query all posts where author is from following
      - (Create/POST) Create a new like on a post
      - (Delete) Delete existing like
      - (Create/POST) Create a new comment on a post
      - (Delete) Delete existing comment

   - Post Detail Screen
      - (Create/POST) Create a new challenge from a post
   - Create Post Screen
      - (Create/POST) Create a new post object
   - Profile Screen
      - (Read/GET) Query logged in user object
         ```swift
         let query = PFQuery(className:"Post")
         query.whereKey("author", equalTo: currentUser)
         query.order(byDescending: "createdAt")
         query.findObjectsInBackground { (posts: [PFObject]?, error: Error?) in
            if let error = error { 
               print(error.localizedDescription)
            } else if let posts = posts {
               print("Successfully retrieved \(posts.count) posts.")
           // TODO: Do something with posts...
            }
         }
         ```
      - (Update/PUT) Update user profile image

- [OPTIONAL: List endpoints if using existing API such as Yelp]
