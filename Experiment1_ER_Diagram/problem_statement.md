# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:

<img width="1340" height="660" alt="image" src="https://github.com/user-attachments/assets/19e3ed57-ef97-4d8c-b776-03f60ee4b247" />


### Entities and Attributes
<img width="1345" height="425" alt="image" src="https://github.com/user-attachments/assets/4b817a0a-48f5-4199-9d9e-c2a2bf73461f" />



### Relationships and Constraints

• Member – Program: Many-to-Many (M:N). Members can join multiple programs such as Yoga
or Zumba.
• Program – Trainer: Many-to-Many (M:N). A program may have multiple trainers and a trainer
may handle multiple programs.
• Trainer – Training Session: One-to-Many (1:N). A trainer can conduct many sessions.
• Member – Training Session: Members may book personal training sessions with trainers.
• Training Session – Attendance: One-to-Many (1:N). Attendance is recorded for each member
for each session.
• Member – Payment: One-to-Many (1:N). Members may make multiple payments for
memberships or sessions.

### Assumptions
• Each member has a unique member ID.
• A member can participate in multiple fitness programs.
• Programs such as Yoga, Zumba, and Weight Training can have multiple trainers.
• Personal training sessions are scheduled between a member and a trainer.
• Attendance records track whether a member attended a particular session.
• Payments include both membership payments and personal training session payments. 

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
<img width="1348" height="835" alt="image" src="https://github.com/user-attachments/assets/d95f269f-0c07-44f5-af76-b0574d0e7928" />


### Entities and Attributes

<img width="571" height="831" alt="image" src="https://github.com/user-attachments/assets/d35cba27-73f3-45d8-8b77-dac9438d5b1b" />


### Relationships and Constraints

● Lending Workflow: A Member (1) can Borrow (N) multiple books over time. Each
Book (1) is linked to its history via the Borrow (N) entity.
● Penalty Logic: The Borrow entity is linked to Overdue in a 1:1 relationship. If a
return date passes the threshold, an overdue record is generated to track the fine
amount.
● Event Management: An Event (M) happens in a specific Room (1). While a room
can host many events, each event occupies only one room at a given time.
● Registration: The Event_registration serves as an associative entity between
Member and Event, allowing for a Many-to-Many (M:N) relationship where many
members attend many events.
● Guest Coordination: The event-speaker table manages the M:N relationship
between Speakers and Events, as a single speaker may give multiple talks, and a
single event (like a panel) may have multiple speakers.


### Assumptions
1. Unique Identifiers: All primary keys (e.g., mem_id, book_id) are assumed to be
unique auto-incrementing integers or UUIDs to prevent collisions.
2. Multi-valued Attributes: The phone attribute is treated as multi-valued, allowing a
member to store more than one contact number without creating redundant member
records.
3. Data Integrity: The loan_id in the Overdue entity is a Foreign Key that also acts as
a Primary Key, ensuring that one loan can only ever have one specific overdue fine
associated with it.
4. Temporal Constraints: It is assumed that the database application logic will check
for "Room" availability based on the date attribute in the Event entity to prevent
double-booking
---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:

<img width="596" height="402" alt="image" src="https://github.com/user-attachments/assets/c161129c-1a73-40a9-88c8-25b96d46d6f4" />

### Entities and Attributes

<img width="553" height="820" alt="image" src="https://github.com/user-attachments/assets/653c0379-afdf-45b6-95bc-661e2452f413" />


### Relationships and Constraints

● Reservation Flow: A Customer (1) can make many (N) Reservations over time.
Each Reservation (M) is assigned to a specific Table (1).
● Service Coordination: Each Reservation (N) is assigned to one Waiter (1) for the
duration of the visit, ensuring accountability for service quality.
● Ordering Logic: A single Reservation (1) can result in multiple Orders (N) (e.g.,
drink rounds followed by food). Each Order (1) contains multiple Order_Items (N)
which act as a bridge to the Dish entity.
● Menu Hierarchy: Many Dishes (N) are grouped under a single Category (1),
allowing the restaurant to organize the menu and report on sales by section.
● Billing Finalization: There is a 1:1 relationship between a Reservation and a Bill.
Once the visit is concluded, all orders linked to that reservation ID are aggregated
into one final billing statement

### Assumptions

● Walk-ins as Reservations: To maintain data integrity for waiter assignments and
table occupancy, walk-in customers are treated as "immediate" reservations within
the system.
● Associative Entity (Order_Item): A many-to-many relationship exists between
Orders and Dishes. We use Order_Item to track specific attributes like quantity and
special instructions (e.g., "no onions").
● Unique Identifiers: All IDs are assumed to be system-generated primary keys to
ensure that even if two customers have the same name, their records remain distinct.
● Service Charge Calculation: The service_charge is an attribute of the Bill rather
than the Order, allowing it to be applied to the subtotal of the entire stay


## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
