Tenant Finder - README
===

# Tenant Finder

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
* User can view potential properties in timeline feed
* submit an application (id, references, work history)
* User can favorite properties
* User can view profile page
* User can view property detail page
* User can upload a property item

**Optional Nice-to-have Stories**
* User can search for properties by location, price
### 2. Screen Archetypes

* Login screen
   * User can login
* Registration screen
   * User can create a new account
 * Property Stream
   * User can view a stream of properties
 * Property Detail 
   * Displays details not in the stream
   * User can create an application
   * User can contact the property manager
 * Property creation
   * User can post a new property 
   * User can upload a description
   * User can upload photos
 * Search
   * User can search by location, price
 * Profile
   * User can view information about their own account
   * User can view other user's profiles
 * Settings
   * User can edit their account

### 3. Navigation

**Tab Navigation** (Tab to Screen)

* Home Feed
* Post a property 
* Search
* Profile detail

**Flow Navigation** (Screen to Screen)

* Login Screen
   * Home
* Registration Screen
   * Home
* Home feed
   * Property detail
* Search
   * Property detail
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
[This section will be completed in Unit 9]
### Models
[Add table of models]
### Networking
- [Add list of network requests by screen ]
- [Create basic snippets for each Parse network request]
- [OPTIONAL: List endpoints if using existing API such as Yelp]
