
<p align="center">
  <img src="https://media-exp1.licdn.com/dms/image/C4D0BAQFua-HoUJGA6Q/company-logo_200_200/0/1639156553027?e=1647475200&v=beta&t=2yjDmA9UkPYz10orLIPk1_QgpH9ovgfy2dYHbnLBJ-s" />
</p>

# LoremIpsum

Lorem Ipsum is a Typescript Web App that allows job applicants to easily curate their experience and skills, build their CV and manage their job applications.

You can find the client repo on the [Lorem Ipsum Client](https://github.com/TomazzoBr/LoremIpsum-Client)


# LoremIpsum-Server API end points

User table

| Table | Method | Endpoint  | Data format to  be sent                                      | Received data                                        | Comments                                              |
| ----- | ------ | --------- | ------------------------------------------------------------ | ---------------------------------------------------- | ----------------------------------------------------- |
| User  | GET    | /user/:id | user_id                                                      | {user_id,email,password,session}          | This will be adapted  to the email once login created |
| User  | POST   | /user     | {email,password} Session will be generated at the backend | {user_id,email,password,session}          |                                                       |
| User  | PUT    | /user/:id | {email,password} to be updated - :id is the user_id to update | updated:  {user_id,email,password,session} |                                                       |
| User  | DELETE | /user/:id | user_id                                                      | N/A                                                  |                                                       |

Categories table

| Method | Endpoint            | Data format to  be sent | Received data   | Comments                                |
| ------ | ------------------- | ----------------------- | --------------- | --------------------------------------- |
| GET    | /:category/:user_id | user_id                 | [] of objects   | gets all certificates of the given user |
| POST   | /:category          | object to create        | new object      |                                         |
| PUT    | /:category/:id      | Object to update        | updated  object |                                         |
| DELETE | /:category/:id      | skill id                | N/A             |                                         |

The categories could be one of the following strings (camel case sensitive) and the object they return:

| Category string format | Returned object data                                         |
| ---------------------- | ------------------------------------------------------------ |
| *certificates*         | {id,name, description}                                       |
| *skills*               | {id,name, description}                                       |
| *education*            | {id, degree, school,city,country,start_date,end_date,description} |
| *languages*            | {id, language_name,level}                                    |
| *personalDetails*      | {id,email,phone_number,image,first_name,last_name,street,postcode,city,country,headline} |
| *savedCV*              | {id, saved_cv, date_created}                                 |
| *workExperience*       | {id,job_title,company,city,country,start_date,end_date,description} |
