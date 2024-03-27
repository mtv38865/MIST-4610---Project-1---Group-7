#MIST4610 Project 1 - Group 7


Problem Description:
The goal of this project is create a relational database for a soccer club. This club desires to have the database so it can run analytics on match revenues, training sessions, contracts, equipments, players, sponsors, and tickets. To test out the database created for the club, our group is tasked as well to generate sample data to populate the table with instances, create queries that would be relevant to the soccer club, and perform these queries on our sample data.


Data Model:
![Final Model (2)](https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/a6c53fbc-2915-4273-9927-9f393e22ddfa)

Explanations:

To begin with, the Team entity is created to store attributes such as team revenue, it shares a one to many relationship with the Coach, Staff, and Player entities. This is because while a team may have many coaches, staff members, and players; these individuals can only belong to one team.


As a soccer club, information about staff members must be kept on hand. In the Staff entity attributes such as name, email address, position, and contract ID are found. Staff members in soccer clubs handle a lot of equipment, meaning that a piece of equipment is also handled by many staff members. This results in the associatve entity EquipmentCheck, between Staff and the Equipment entity whichs stores instances of equipmentCost and the date it is acquired. The associative entity is useful for the club as they can monitor how often equipment is checked, and which pieces of equipment are having the most issues, prompting a need for replacement or service.

One of the central entities of the model we created is the Contract entity. This entity stores critical data about the contracts including the amount, length, and lawyer involved between the various players, staff, coaches, and sponsors associated with the soccer club. Given that an individual whether a player, staff member, coach, or sponsor can only hold one contract at a given time but contracts are signed to many of these entitites the relationship is modeled with a one to many non-identifying relationship.

A soccer club usually has many coaches, including some for offense, defense, or conditioning. There is also always a head coach as well, to model this a one to many recursive relationship is created on the Coach entity. Here in the Coach entity valuable data is stored such as coach position, email address, phone number, as well their contract ID as part of a foreign key. Coaches are only a part of one team while a team will have many coaches, therefore Team and Coaches are modeled to have a one to many relationship. Coaches are also in charge of many players and many players are under many coaches, because of this a many to many relationship is modeled and an associative entity called Training is created. In the associative entity training, information about each training session is stored such as the duration in minutes, the type of training session, and the players and coaches in the session.

Soccer clubs have to book their matches at stadiums prior the season beginng, since a club wants to sell the most tickets higher capacity stadiums are typically favored. In the Stadium entity, this and the country the stadium is located in is detailed as attributes. Stadiums can have many matches, while matches can only take place in one stadium, meaning there is a one to many relationship between stadium and matches. In the Matches entity, attributes such as match revenue, date, head referee, total attendance, as well as the number of various types of tickets sold are stored.

Clubs are particulary interested in being able to track data for their players, both for marketing and managerial purposes. The players entity stores data such as total goals scored, blocked, or balls stolen from an opposing player. It also has a foreign key to contract so the club can see how long they are signed to the team for, and what they have to pay them per year. Players on soccer teams also get sponsors, however a player is typically only partnered with only one sponsor while a sponsor can be partnered with many players. This one to many relationship is also present through a foreign key on the player entity. 







