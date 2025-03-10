# API

### Authentication Endpoints

The Authentication flow for the application is:

### User Signup/Login

METHOD | ENDPOINT         | TOKEN | ROLE | DESCRIPTION              | POST PARAMS                                     | RETURNS
-------|------------------|-------|------|--------------------|-------------------------------------------------|--------------------
POST   | /auth/signup     | -     | user | User Signup              | `firstName`,`lastName`, `email`, `password`, `phone`, `birth_Date` , `debut_date`  | { token: `token` }
POST   | /auth/login      | -     | user | User Login               | `email`, `password`                             | { token: `token` }

### User Endpoints

METHOD | ENDPOINT         | TOKEN | ROLE | DESCRIPTION              | POST PARAMS                                     | RETURNS
-------|------------------|-------|------|--------------------------|-------------------------------------------------|--------------------
GET    | /user            | YES   | admin | Get All Users            |  `query params`                            | [{user}]
GET    | /user/me    | YES   | user | Get Own Profile          |                                                |  {user}
GET    | /user/:userId        | YES   | admin | Get One User             |                                             |  {user}
POST   | /user            | YES   | admin | Create one user         |`firstName`,`lastName`, `email`, `password`, `phone`, `birth_Date` , `debut_date` | {user}
PUT    | /user/me    | YES   | user | Update own profile       |`firstName`,`lastName`, `email`, `password`, `phone`, `birth_Date` , `debut_date` | {message: 'Profile updated'}
PUT    | /user/password   | YES   | user  | Reset password          | `newPassword` `repeatPassword`                                    | { message: 'Password updated }
PUT    | /user/:userId       | YES   | admin | Update one user         |  `firstName`,`lastName`, `email`, `password`, `phone`, `birth_Date` , `debut_date` | {message: 'User updated'
DELETE | /user/:userId      | YES   | admin | Delete one user         |                                                   | {message: 'User deleted'}
DELETE | /user/me   | YES   | user | Delete own profile       |                                                    | { message: 'Profile deleted' }

### Medical Info Endpoints

METHOD | ENDPOINT         | TOKEN | ROLE | DESCRIPTION              | POST PARAMS                                     | RETURNS
-------|------------------|-------|------|--------------------------|-------------------------------------------------|--------------------
GET    | /medical     | YES   | admin | Get All Users Medical Info           |  `query params`                          | [{medical_info}]
GET    | /medical/me   | YES   | user | Get Own Medical Info         |                                                |  {medical_info}
GET    | /medical/:userId        | YES   | admin | Get One User Medical Info            |                                             |  {medical_info}
POST   | /medical            | YES   | user | Create own Medical Info        |`pump_model`, `basal_insulin`, `bolus_insulin`, `good_sv`, `high_sv`, `low_sv` , `breakfast`, `luch`, `snack`, `dinner`, `extra` | {medical_info}
POST   | /medical/:userId           | YES   | admin | Create one user Medical Info        |`pump_model`, `basal_insulin`, `bolus_insulin`, `good_sv`, `high_sv`, `low_sv` , `breakfast`, `luch`, `snack`, `dinner`, `extra` | {medical_info}
PUT    | /medical/me    | YES   | user | Update own Medical Info       |`pump_model`, `basal_insulin`, `bolus_insulin`, `good_sv`, `high_sv`, `low_sv` , `breakfast`, `luch`, `snack`, `dinner`, `extra`| {message: 'Medical info updated'}
PUT    | /medical/:userId       | YES   | admin | Update one user Medical Info       |`pump_model`, `basal_insulin`, `bolus_insulin`, `good_sv`, `high_sv`, `low_sv` , `breakfast`, `luch`, `snack`, `dinner`, `extra` | {message: 'Medical_info updated'
DELETE | /medical/:userId      | YES   | admin | Delete one user Medical Info       |                                                   | {message: 'Medical_info deleted'}
DELETE | /medical/me    | YES   | user | Delete own Medical Info       |                                                    | { message: 'Medical_info deleted' }

### Comment Endpoints

METHOD | ENDPOINT         | TOKEN | ROLE | DESCRIPTION              | POST PARAMS                                     | RETURNS
-------|------------------|-------|------|--------------------|-------------------------------------------------|--------------------
GET   | /comment     | YES     | admin | Get all Comments              |  `query params`  | [{comments}]
GET   | /comment/me     | YES      | user | Get own Comments               |                            | [{comments}]
GET   | /comment/:userId     | YES      | admin | Get user id Comments               |                            | [{comments}]
POST   | /comment     | YES      | user | Create a comment              |  | {comment}
POST   | /comment/:userId   | YES      | admin | Create a comment              |  | {comment}
PUT   | /comment/me/:commentId    | YES      | user | Update own comment              |                            | {message: 'Your comment have been updated'}
PUT   | /comment/:commentId    | YES      | admin | Update a specific comment              |                            | {message: 'The comment have been updated'}
DELETE   | /comment/me/:commentId    | YES      | user | Delete a specific comment             |                            | {message: 'Comment deleted'}
DELETE   | /comment/:commentId     | YES      | admin | Delete a specific comment             |                            | {message: 'Comment deleted'}

### Objetive Endpoints

METHOD | ENDPOINT         | TOKEN | ROLE | DESCRIPTION              | POST PARAMS                                     | RETURNS
-------|------------------|-------|------|--------------------|-------------------------------------------------|--------------------
GET    | /objetive/me            | YES   | user | Calculate own objetive          |                             | { message: + Objetive Image }
GET    | /objetive/:userId    | YES   | admin | Calculate user id objetive         |                                            | { message: + Objetive Image }
GET    | /objetive/all            | YES   | user | See the current objective of all users          |                        | [{user_objetive}]
GET    | /objetive/all/?            | YES   | user | See the current objective of all users filtered          |    `query params`              | [{user_objetive}]

### Utilities Endpoints

METHOD | ENDPOINT         | TOKEN | ROLE | DESCRIPTION              | POST PARAMS                                     | RETURNS
-------|------------------|-------|------|--------------------------|-------------------------------------------------|--------------------
GET    | /insulin/me            | YES   | user | Calculate own total insulin          |                             | { message: "Your total insulin is:" }
GET    | /insulin/:userId    | YES   | admin | Calculate user id total insulin          |                                            | { message: "User id total insulin is:" }
GET    | /ratio/me            | YES   | user | Calculate own ratio          |                             | { message: "Your ratio is:" }
GET    | /ratio/:userId    | YES   | admin | Calculate user id ratio          |                                            | { message: "User id ratio is:" }
GET    | /resistance/me       | YES   | user | Calculate own insulin resistance          |                                            | { message: "Your insulin resistance is:" }
GET    | /resistance/:userId    | YES   | admin | Calculate user id insulin resistance   |                                            |  { message: "User id insulin resistance is:" }
GET    | /ch/me            | YES   | user | Calculate total CH          |                             | { message: "The carbohydrates you have consumed are:" }
GET    | /ch/id    | YES   | admin | Calculate user id total CH          |                                            | { message: "The carbohydrates user id have consumed are:" }
GET    | /time/me            | YES   | user | Calculate how long user have been receiving treatment         |                             | { message: "You have been receiving treatment for:" }
GET    | /time/:userId    | YES   | admin | Calculate how long (user id) have been receiving treatment|                                            | { message: "User id have been receiving treatment for:" }


