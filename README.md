#MIST4610 Project 1 - Group 7


Problem Description:
The goal of this project is create a relational database for a soccer club. This club desires to have the database so it can run analytics on match revenues, training sessions, contracts, equipments, players, sponsors, and tickets. To test out the database created for the club, our group is tasked as well to generate sample data to populate the table with instances, create queries that would be relevant to the soccer club, and perform these queries on our sample data.


Data Model:
![Final Model (2)](https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/a6c53fbc-2915-4273-9927-9f393e22ddfa)

Explanations:

One of the central entities of the model we created is the Contract entity. This entity stores critical data about the contracts involved between the various players, staff, coaches, and sponsors associated with the soccer club. Given that an individual whether a player, staff member, coach, or sponsor can only hold one contract at a given time but contracts are signed to many of these entitites the relationship is modeled with a one to many non-identifying relationship.

A soccer club usually has many coaches, including some for offense, defense or conditioning. There is also always a head coach as well, to model this a one to many recursive relationship is created on the Coach entity. Here in the Coach entity valuable data is stored such as coach position, email address, phone number, as well their contract ID as part of a foreign key. Coaches are only a part of one team while a team will have many coaches, therefore Team and Coaches are modeled to have a one to many relationship. Coaches are also in charge of many players and many players are under many coaches, because of this a many to many relationship is modeled and an associative entity called Training is created. In the associative entity training, information about each training session is stored such as the duration in minutes, the type of training session, and the players and coaches in the session.




