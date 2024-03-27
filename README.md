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
![Final Model (2)](https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/a6c53fbc-2915-4273-9927-9f393e22ddfa)

Explanations:

Our model is structured around a hypothetical soccer club that wishes to store data about matches, players, equipment, contracts, and other important aspects of a soccer club.

To begin with a soccer club must store data about it's team, the Team entity is created to store attributes such as team revenue, it shares a one to many relationship with the Coach, Staff, and Player entities. This is because while a team may have many coaches, staff members, and players; these individuals can only belong to one team.


As a soccer club, information about staff members must be kept on hand. In the Staff entity attributes such as name, email address, position, and contract ID are found. Staff members in soccer clubs handle a lot of equipment, meaning that a piece of equipment is also handled by many staff members. This results in the associatve entity EquipmentCheck, between Staff and the Equipment entity whichs stores instances of equipmentCost and the date it is acquired. The associative entity is useful for the club as they can monitor how often equipment is checked, and which pieces of equipment are having the most issues, prompting a need for replacement or service.

One of the central entities of the model we created is the Contract entity. This entity stores critical data about the contracts including the amount, length, and lawyer involved between the various players, staff, coaches, and sponsors associated with the soccer club. Given that an individual whether a player, staff member, coach, or sponsor can only hold one contract at a given time but contracts are signed to many of these entitites the relationships are modeled with one to many non-identifying relationships.

A soccer club usually has many coaches, including some for offense, defense, or conditioning. There is also always a head coach as well, to model this a one to many recursive relationship is created on the Coach entity. Here in the Coach entity valuable data is stored such as coach position, email address, phone number, as well their contract ID as part of a foreign key. Coaches are also in charge of many players and many players are under many coaches, because of this a many to many relationship is modeled and an associative entity called Training is created. In the associative entity training, information about each training session is stored such as the duration in minutes, the type of training session, and the players and coaches in the session.

Soccer clubs have to book their matches at stadiums prior to the season beginning, since a club wants to sell the most tickets higher capacity stadiums are typically favored. In the Stadium entity, stadium capacity and the country the stadium is located in is detailed as attributes. Stadiums can have many matches take place, while a particular matches can only take place in one stadium, meaning there is a one to many relationship between stadium and matches. In the Matches entity, attributes such as match revenue, date, head referee, total attendance, as well as the number of various types of tickets sold are stored.

Clubs are particulary interested in being able to track data for their players, both for marketing and managerial purposes. The players entity stores data such as total goals scored, blocked, or balls stolen from an opposing player. It also has a foreign key to contract so the club can see how long they are signed to the team for, and what their yearly salary is. Players on soccer teams also get sponsors, however a player is typically only partnered with only one sponsor while a sponsor can be partnered with many players. This one to many relationship is also present through a foreign key on the player entity. Furthermore, players play in many matches with many of their team mates, meaning a many to many relationship exists between the two entities. The associative relationship GameStats shows this and allows for the tracking of player game statistics such as the numer of goals they scored in one match at a particular stadium.

Data Dictionary:

<img width="636" alt="Screenshot 2024-03-27 at 8 21 32 AM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/d11f4cbf-f444-4573-9013-364e046cdc72">

<img width="618" alt="Screenshot 2024-03-27 at 8 29 16 AM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/a17d031c-59d7-4405-8bd4-a3845a54f272">

<img width="620" alt="Screenshot 2024-03-27 at 8 32 42 AM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/92f70d2d-b4ed-4799-b77f-614152d697bb">

<img width="624" alt="Screenshot 2024-03-27 at 8 36 56 AM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/3c6b705c-aa4f-428e-a5da-74bc3666fc3d">

<img width="633" alt="Screenshot 2024-03-27 at 8 43 26 AM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/a9afaf7d-e34d-43d9-9b95-e40badaf3ddd">

<img width="632" alt="Screenshot 2024-03-27 at 8 47 26 AM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/f1323300-5a64-45d9-8bb0-d109a9b03162">

<img width="550" alt="Screenshot 2024-03-27 at 8 55 44 AM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/03b2ae55-3417-49a3-8ec2-918bcabcc758">

<img width="505" alt="Screenshot 2024-03-27 at 8 57 35 AM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/55a4a7df-5476-409e-b686-de67e1493ac4">

<img width="547" alt="Screenshot 2024-03-27 at 9 01 25 AM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/e59bd155-9d5e-4562-a932-00b322b7d86b">


<img width="519" alt="Screenshot 2024-03-27 at 8 59 16 AM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/cb7f6228-0ff3-499d-8ea5-a55f20453721">



<img width="554" alt="Screenshot 2024-03-27 at 9 02 47 AM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/1abe33e0-52c0-4c1e-b36d-51c2e9ec0354">

<img width="556" alt="Screenshot 2024-03-27 at 9 04 52 AM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/0f7f8a66-2433-45ac-9939-fc9777b3f3d7">




<img width="519" alt="Screenshot 2024-03-27 at 8 59 16 AM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/cb7f6228-0ff3-499d-8ea5-a55f20453721">

























