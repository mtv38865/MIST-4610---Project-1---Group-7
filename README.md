# **MIST4610 Project 1 - Group 7**

# **Team Members:**

**GROUP:**
Sp24_21484_Group7

Ryan Dyals [@RyanDyals](https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/tree/main)
Stuti Bhat [@Stutibhat2](https://github.com/stutibhat2/MIST-4610-Group-7-Project-1)
Eujin Kang [@EujinKang](https://github.com/eujinkang/MIST-4610-Group7-Project-1-G)
Brandon Yum [@BrandonYum](https://github.com/BRANDONYUM/Team-7-MIST-4610-Group-Project-1)
Matthew Vega[@mtv38865](https://github.com/mtv38865/MIST-4610---Project-1---Group-7)

# **Problem Description:**
The goal of this project is create a data model and convert it into a functioning relational database for a soccer club. This club desires to have the database so it can run analytics on match revenues, game statistics, training sessions, contracts, equipment, players, sponsors, and tickets. To test out the database created for the club, our group is tasked as well to generate sample data to populate the tables with instances, create queries that would be relevant to the soccer club, and perform these queries on our sample data.


# **Data Model:**
![Final Model (2)](https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/86173fd0-ab51-42ed-816d-70ac1625be0d)


# **Explanations:**

Our model is structured around a hypothetical soccer club that wishes to store data about matches, players, equipment, contracts, and other important aspects of a soccer club.

To begin with a soccer club must store data about it's team, the Team entity is created to store attributes such as team revenue, it shares a one to many relationship with the Coach, Staff, and Player entities. This is because while a team may have many coaches, staff members, and players; these individuals can only belong to one team.


As a soccer club, information about staff members must be kept on hand. In the Staff entity attributes such as name, email address, position, and contract ID are found. Staff members in soccer clubs handle a lot of equipment, meaning that a piece of equipment is also handled by many staff members. This results in the associatve entity EquipmentCheck, between Staff and the Equipment entity whichs stores instances of equipmentCost and the date it is acquired. The associative entity is useful for the club as they can monitor how often equipment is checked, and which pieces of equipment are having the most issues, prompting a need for replacement or service.

One of the central entities of the model we created is the Contract entity. This entity stores critical data about the contracts including the amount, length, and lawyer involved between the various players, staff, coaches, and sponsors associated with the soccer club. Given that an individual whether a player, staff member, coach, or sponsor can only hold one contract at a given time but contracts are signed to many of these entitites the relationships are modeled with one to many non-identifying relationships.

A soccer club usually has many coaches, including some for offense, defense, or conditioning. There is also always a head coach as well, to model this a one to many recursive relationship is created on the Coach entity. Here in the Coach entity valuable data is stored such as coach position, email address, phone number, as well their contract ID as part of a foreign key. Coaches are also in charge of many players and many players are under many coaches, because of this a many to many relationship is modeled and an associative entity called Training is created. In the associative entity training, information about each training session is stored such as the duration in minutes, the type of training session, and the players and coaches in the session.

Soccer clubs have to book their matches at stadiums prior to the season beginning, since a club wants to sell the most tickets higher capacity stadiums are typically favored. In the Stadium entity, stadium capacity and the country the stadium is located in is detailed as attributes. Stadiums can have many matches take place, while a particular matches can only take place in one stadium, meaning there is a one to many relationship between stadium and matches. In the Matches entity, attributes such as match revenue, date, head referee, total attendance, as well as the number of various types of tickets sold are stored.

Clubs are particulary interested in being able to track data for their players, both for marketing and managerial purposes. The players entity stores data such as total goals scored, blocked, or balls stolen from an opposing player. It also has a foreign key to contract so the club can see how long they are signed to the team for, and what their yearly salary is. Players on soccer teams also get sponsors, however a player is typically only partnered with only one sponsor while a sponsor can be partnered with many players. This one to many relationship is also present through a foreign key on the player entity. Furthermore, players play in many matches with many of their team mates, meaning a many to many relationship exists between the two entities. The associative relationship GameStats shows this and allows for the tracking of player game statistics such as the numer of goals they scored in one match at a particular stadium.

# **Data Dictionary:**


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



# **Queries:**
<img width="771" alt="Screenshot 2024-03-27 at 7 15 33 PM" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/a7d27584-ee5e-4ed4-b9d4-018769951179">



**#1** This query lists a player's id if they have a inactive contract, it also includes the player's phone number and the lawyer for their contract.
<img width="1116" alt="Query 1" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/73eee8a9-02ad-4e50-a378-231cd339495f">


Query 1 is significant for the managerial aspect of a soccer club as they must handle players who either have not signed their offered contract or have a contract that recently expired. This query allows the club to see these player's and contact them regarding their contract.


**#2** This query retrieves the total number of goals scored by ecah player in each match and lists them in descending order of total goals scored.
<img width="1107" alt="Query 2" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/3b7c4427-67d8-4ffb-8a85-331b679edebd">

Query 2 allows for the soccer club to keep track of key statistics by match for each player. This one specifcally tracks goals scored. This query allows for management to quickly look at match data for each player by a metric such as goals scored.


**#3** This query shows stadiums that held at least one match that sold over 30,0000 premium tickets and orders them from greatest to least.
<img width="707" alt="Query 3" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/38ee40d3-c851-4905-aa5f-c642b3bd8ccf">

Query 3 allows for the soccer club to see what stadium and in what countries premium tickets are above a certain threshold. This can allow them to select matches and stadiums in the next season that are more likely to sell more premium tickets.

**#4** This query shows all players who have scored less than three goals.
<img width="704" alt="Query 4" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/ca0b5311-8f1a-40be-ba78-cf947aa2f9c4">

Soccer clubs often have to analyze which players need more training or need to be cut from the team. Query 4 allows for the club to see underperforming players so they can make a decision on whether to cut them or offer more training to improve their performance.

**#5** This query shows the top two pieces of equipment that have issues in the soccer club. It also lists the staff member that checked the equipment and found an issue.
<img width="1136" alt="Query 5" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/345b27a6-023a-4ebe-82af-10fc1915e3b1">

Query 5 allows for the management of the soccer club to see what pieces of equipment are having the most trouble as well as the staff member who checked them. This allows them to see what pieces need to be serviced or replaced and what staff member should contacted about the issue.

**#6** This query shows the first and last names of players, and the amount of their contract who have a contract amount greater than the of average all contracts within the soccer club.
<img width="714" alt="Query 6" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/0b9b5b6c-0751-4d5d-bbb8-2a983121bda7">

Query 6 can be useful for a soccer club's recruitment process. New and upcoming players often want to know that they can end up making if they join and stay on the team. This query allows management to show prospective players other players that are currently on the team and how they much they make relative to everyone else. 

**#7** This query lists the bottom four players on the team in terms of total time spent in agility training sessions and their respective time spent in agility training. It is ordered by least to greatest.

<img width="705" alt="Query 7 1" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/c765fd77-33a6-41ec-ad29-60513f1d192e">

Query 7 allows for management in soccer club to analyze players that are not getting adequate training. By analyzing who has the least total time spent in agility training, coaches or other staff can see what players need to be scheduled for further training.

**#8** This query lists the player's first name, last name, and their who played a match in Mexico where the attendance in the match was higher than average attendance for all matches in Mexico.

<img width="1186" alt="8-3" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/904120ac-cdb9-40b0-943d-4d0bd9d31812">

Query 8 is great for a soccer club's marketing purposes. This query allows the club to see what players are playing in Mexico and producing an attendance rate for the match higher than the average for that country. The club then can tailor advertisements to these players in Mexico.


**#9** This query lists the match date, stadium ID, matchRevenue, matchID, and player name for matches where revenue was greater than the average of all matches and at least one goal was scored.
<img width="739" alt="Query 9" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/dc636ff5-2bb1-466f-89c8-5f6c70a1eaf9">

Query 9 allows for management of the soccer club to quickly see games that had meaningful action also garnered high revenue. This means that when the editing team is creating videos it can quickly identify what games at least had the team score one goal and also brought high revenue. This would make the editing team more efficient and have less time deciding what matches to pull clips from.

**#10** This query lists the contractID,contract amount, contract length coachID, and coach position for coaches whose contracts only has 2 years or less remaining.

<img width="708" alt="Query 10" src="https://github.com/RyanDyals/MIST-4610---Project-1---Group-7/assets/134531824/5df5ed36-57c3-4fb6-8c1c-b86712ff56a8">


Query 10 allows managment to strategize ahead of time of what coaches they need to look at offering new contracts to or coaches that they need to replace. The soccer club can look at a coach's current contract amount and forecast what will be budgetable in the future or if they can even afford to resign the coach when the contract is up.


# **Database Information**
Name of database: ns_Sp24_21484_Group7

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_Q1();












