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
  <img width="1100" height="662" alt="image" src="https://github.com/user-attachments/assets/d9591460-7c99-45e6-8029-b6e5b6afb633" />



### Entities and Attributes

<img width="1105" height="372" alt="image" src="https://github.com/user-attachments/assets/6627770e-32d4-430c-8ab0-360c902f9228" />


### Relationships and Constraints

<img width="1107" height="377" alt="image" src="https://github.com/user-attachments/assets/8934ed98-5b18-4055-ba0b-42fc8858460f" />


### Assumptions
Each session involves exactly one trainer and one member.
Programs are predefined (Yoga, Zumba, Weight Training, etc.).
Payments are only for membership or session bookings.

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
<img width="1056" height="702" alt="image" src="https://github.com/user-attachments/assets/ddc67bb3-bd95-48f2-b56b-efd117b1d2f9" />


### Entities and Attributes

<img width="928" height="305" alt="image" src="https://github.com/user-attachments/assets/a46d3da1-28d2-47ef-b75e-1c780c58ad36" />


### Relationships and Constraints

<img width="762" height="175" alt="image" src="https://github.com/user-attachments/assets/8cb44c6a-e9ce-4f58-a223-f5963049e77b" />

### Assumptions
Books can be borrowed multiple times by different Members.
Each Event happens in one Room at a specific time.
A Speaker can participate in multiple Events.


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
<img width="1102" height="545" alt="image" src="https://github.com/user-attachments/assets/7dcbcb67-a4ca-4607-8b44-b363c330fdfd" />


### Entities and Attributes

<img width="927" height="266" alt="image" src="https://github.com/user-attachments/assets/2d63e623-9f3d-4245-b058-ad9095dd661f" />

### Relationships and Constraints

<img width="802" height="205" alt="image" src="https://github.com/user-attachments/assets/b7e1b8c8-ac1a-421d-84fa-c9c49c596964" />

### Assumptions
One reservation uses one table and one waiter.
Bill is generated automatically after service.
Customer details stored for every reservation.

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
