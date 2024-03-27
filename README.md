#MIST4610 Project 1 - Group 7

Team Members:

Ryan Dyals @RyanDyals
Stuti Bhat @Stutibhat2
Eujin Kang @
Brandon @
Matthew Vega @

Problem Description:
The goal of this project is create a data model and convert it into a functioning relational database for a soccer club. This club desires to have the database so it can run analytics on match revenues, training sessions, contracts, equipment, players, sponsors, and tickets. To test out the database created for the club, our group is tasked as well to generate sample data to populate the tables with instances, create queries that would be relevant to the soccer club, and perform these queries on our sample data.


Data Model:
![Final Model (2)](https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/86173fd0-ab51-42ed-816d-70ac1625be0d)


Explanations:

Our model is structured around a hypothetical soccer club that wishes to store data about matches, players, equipment, contracts, and other important aspects of a soccer club.

To begin with a soccer club must store data about it's team, the Team entity is created to store attributes such as team revenue, it shares a one to many relationship with the Coach, Staff, and Player entities. This is because while a team may have many coaches, staff members, and players; these individuals can only belong to one team.


As a soccer club, information about staff members must be kept on hand. In the Staff entity attributes such as name, email address, position, and contract ID are found. Staff members in soccer clubs handle a lot of equipment, meaning that a piece of equipment is also handled by many staff members. This results in the associatve entity EquipmentCheck, between Staff and the Equipment entity whichs stores instances of equipmentCost and the date it is acquired. The associative entity is useful for the club as they can monitor how often equipment is checked, and which pieces of equipment are having the most issues, prompting a need for replacement or service.

One of the central entities of the model we created is the Contract entity. This entity stores critical data about the contracts including the amount, length, and lawyer involved between the various players, staff, coaches, and sponsors associated with the soccer club. Given that an individual whether a player, staff member, coach, or sponsor can only hold one contract at a given time but contracts are signed to many of these entitites the relationships are modeled with one to many non-identifying relationships.

A soccer club usually has many coaches, including some for offense, defense, or conditioning. There is also always a head coach as well, to model this a one to many recursive relationship is created on the Coach entity. Here in the Coach entity valuable data is stored such as coach position, email address, phone number, as well their contract ID as part of a foreign key. Coaches are also in charge of many players and many players are under many coaches, because of this a many to many relationship is modeled and an associative entity called Training is created. In the associative entity training, information about each training session is stored such as the duration in minutes, the type of training session, and the players and coaches in the session.

Soccer clubs have to book their matches at stadiums prior to the season beginning, since a club wants to sell the most tickets higher capacity stadiums are typically favored. In the Stadium entity, stadium capacity and the country the stadium is located in is detailed as attributes. Stadiums can have many matches take place, while a particular matches can only take place in one stadium, meaning there is a one to many relationship between stadium and matches. In the Matches entity, attributes such as match revenue, date, head referee, total attendance, as well as the number of various types of tickets sold are stored.

Clubs are particulary interested in being able to track data for their players, both for marketing and managerial purposes. The players entity stores data such as total goals scored, blocked, or balls stolen from an opposing player. It also has a foreign key to contract so the club can see how long they are signed to the team for, and what their yearly salary is. Players on soccer teams also get sponsors, however a player is typically only partnered with only one sponsor while a sponsor can be partnered with many players. This one to many relationship is also present through a foreign key on the player entity. Furthermore, players play in many matches with many of their team mates, meaning a many to many relationship exists between the two entities. The associative relationship GameStats shows this and allows for the tracking of player game statistics such as the numer of goals they scored in one match at a particular stadium.

Data Dictionary:


<img width="629" alt="Coach" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/4304517a-5b18-4225-998b-561808f54257">

<img width="548" alt="Contract" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/ef7b213d-cbe5-4fc4-82c3-94c5a09d6212">

<img width="597" alt="Equipment" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/38ee890f-24c5-4b7b-a463-7b682a7a6a31">

<img width="588" alt="EquipmentCheck" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/ed9a7a96-9790-4d93-89fa-00a82d85a095">

<img width="623" alt="GameStats" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/04f3281f-75a4-4dcb-930a-7e907efc723c">

<img width="609" alt="Matches" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/e093c478-9f09-47bf-bc7d-dd39af48f887">

<img width="618" alt="Player" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/44104f89-850d-44b1-93e9-a59fa322b403">

<img width="571" alt="Sponsor" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/6358c457-7307-446c-9e11-ed66b9773a7b">

<img width="573" alt="Staff" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/45464e76-2f9c-48b9-87d4-35d87e691569">

<img width="604" alt="Stadium" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/ba68ee5a-fe1f-4f51-9849-d1f0cffaa5d2">

<img width="596" alt="Team" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/832980ce-6de5-4c5c-8e92-d49ed758ab63">

<img width="628" alt="Training" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/cdd737aa-0e56-4156-9827-58b7580bdf00">



























