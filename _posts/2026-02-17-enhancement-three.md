---
layout: post
title: "Enhancement Three - Using the MEAN Stack"
author: "Arka Tu"
categories: projects
tags: [projects]
image: header-01.png
---
[GitHub Repository](https://github.com/arka2/cs465-fullstack)

## Briefly describe the artifact. What is it? When was it created?
This artifact was created at the end of 2025 when I took CS-465 Full-Stack Development I at SNHU. It’s a web application with both a customer-facing site and an admin-facing site. The customer-facing site is a static HTML site, and the admin-facing site is a single page application (SPA). The SPA allows administrators to view, add, edit, and delete trips from the database. The application uses the MEAN stack (MongoDB, Express, Angular, and Node.js).

## Justify the inclusion of the artifact in your ePortfolio. Why did you select this item? What specific components of the artifact showcase your skills and abilities in databases? How was the artifact improved?
I included this project in my portfolio because it was one of the more complete projects from a previous course that involved a database. Web development is also something I considered as a career, and, while I’m more interested in technical art, I’m still curious about web development. This project fits both my interests and the database requirement for this category.

Originally, the application connected to a MongoDB database to retrieve trip and user information. The SPA rendered a list of cards, with each card containing information for one trip. The user information was accessed when a user logged in. When I finished the CS-465 course, the application accessed the database and retrieved the information correctly, but the list of trips did not render without a forced reload. The application also lacked the ability to delete trips, which meant that there was not full CRUD functionality.

My enhancement of this project involved adding the ability to delete trips, adding resorts to the database, and adding a new page to the SPA to show available resorts. The ability to delete trips makes it much easier for admins to interact with the database, since the original application lacked an essential feature. Admins can now delete trips through the application instead of needing to go into the database directly to delete it, which might be difficult for administrators if they're not technically-savvy, or needing to have a developer go in to delete the trip, which takes their efforts away from other tasks. Reducing the friction to delete trips makes it easier for administrators to keep trips up-to-date. The application connects directly to the database, which means that the database and the application update as changes are made to either of them. As I built the CRUD applications, I tested that the API endpoints worked by using Postman, where I would send requests to retrieve and update data. After ensuring the endpoints worked, I then used the CRUD actions in the application and checked MongoDB Compass to ensure that the changes were reflected in the database. The addition of resorts also make it easier for an organization to make decisions regarding trips and resorts since they can easily access resort information. Additionally, I fixed the rendering issue, which I tested by starting the application locally and observing the console output, which would print when it retrieved trip information. Visually, the application also didn't require a forced reload to display the trips.

## Did you meet the course outcomes you planned to meet with this enhancement in Module One? Do you have any updates to your outcome-coverage plans?
The course outcomes I planned to meet with this artifact were:
1. Employ strategies for building collaborative environments that enable diverse audiences to support organizational decision making in the field of computer science
3. Design and evaluate computing solutions that solve a given problem using algorithmic principles and computer science practices and standards appropriate to its solution, while managing the trade-offs involved in design choices (data structures and algorithms)
4. Demonstrate an ability to use well-founded and innovative techniques, skills, and tools in computing practices for the purpose of implementing computer solutions that deliver value and accomplish industry-specific goals (software engineering/design/database)
5. Develop a security mindset that anticipates adversarial exploits in software architecture and designs to expose potential vulnerabilities, mitigate design flaws, and ensure privacy and enhanced security of data and resources

I met Course Outcome 1 by adding full CRUD functionality and adding the ability to view available resorts. These both help the company make decisions by giving employees easy access to trip and resort information. Employees don’t need to interact with the database directly, which can be difficult for non-technical employees. The application also authenticates users, which mitigates unauthorized changes to the database.

I met Course Outcome 3 by using both a static HTML website for the customer-facing site and an SPA for the admin-facing site. In using both, I can better understand the trade-offs when using one or the other, and, in the future, I can make informed decisions about which I should use for a project.

I met Course Outcome 4 by using the MEAN stack. The MEAN stack is standard in web development, and it’s important for me to understand how each piece works together. This project also gave me more experience with MongoDB, as I had only used it in one course before CS-465. I also hadn’t used Express or Angular before that course, so this project demonstrates my ability to use both of those.

I met Course Outcome 5 by ensuring that a user cannot add, edit, or delete a trip without being authenticated. The original project had a defect where nothing would happen if a logged in user tried to add, edit, or delete a trip, but this defect only occurred after introducing JWTs (JSON Web Tokens) to authenticate users. The modified project fixes this, and logged in users can now perform those functions.

## Reflect on the process of enhancing and modifying the artifact. What did you learn as you were creating it and improving it? What challenges did you face?
Throughout the CS-465 course, I struggled with the problem of the trip cards not rendering. I had spoken with classmates about this, and they had the same issue. Someone had suggested downgrading Angular to the version that was used in the demonstration and guides. I tried that during the course, but it had broken other functionality. As I was working on this project for my capstone, I attempted to downgrade Angular again. This time, it didn’t break any functionality, and I’m not entirely sure what I did differently.

I originally planned to use a MySQL database and switch it out with the existing MongoDB database. However, despite looking through documentation for both MySQL and Sequelize, I could not figure out how to implement the new database. I had trouble translating the syntax used to get the MongoDB schema information. Ultimately, I resorted to reinforcing what I learned in CS-465 and continued to use MongoDB for this enhancement.
