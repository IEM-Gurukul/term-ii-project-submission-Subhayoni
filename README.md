[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/pG3gvzt-)
# PCCCS495 – Term II Project

## Project Title
Smart Personal Expense Manager

---

## Problem Statement (max 150 words)
Keeping track of daily expenses is something most of us know we should do,
but rarely actually do. I built this project to solve that — a simple,
offline Java console app where you can log your income and expenses, sort
them by category, and always know your current balance. No internet needed,
no complicated setup. Data is saved to a file so nothing is lost when you
close the app. The focus was on making it actually usable — clean inputs,
helpful error messages, and a menu that doesn't require a manual to navigate.
Security here means making sure bad inputs don't crash the program and that
saved data stays intact between sessions.

---

## Target User
Students and young working professionals who want a dead-simple way to
track where their money is going — no app download, no account, just run
and use.

---

## Core Features

- Log income and expense entries with amount, category, date and a short note
- Filter transactions by category or type and see totals at a glance
- Persistent file storage — your data is right there the next time you open it
- Live balance tracker that updates as you add or remove entries
- Input validation that catches empty fields and negative amounts before they cause problems

---

## OOP Concepts Used

- Abstraction: Transaction is abstract — subclasses decide what type they are via getType()
- Inheritance: Income and Expense both extend Transaction and reuse all its fields
- Polymorphism: A single List holds both types — getType() behaves differently per object at runtime
- Exception Handling: InvalidTransactionException is thrown for invalid amount or blank category, caught in the menu layer
- Collections: ArrayList is used to store, iterate, filter and manage all transaction records

---

## Proposed Architecture Description
The app is structured around a clean MVC separation across four packages:

- model/ — the data layer: Transaction (abstract), Income, Expense, User
- controller/ — all the logic lives here: ExpenseManager handles adding, removing, filtering and balance
- view/ — MenuView runs the console interface, takes user input, calls the controller
- persistence/ — FileHandler saves and loads the transaction list using Java Serialization

Each layer only talks to the one next to it, so changing one part doesn't break everything else.

---

## How to Run

1. Clone this repository
2. Open in VS Code or IntelliJ with the Java extension installed
3. From the src/ directory, compile:
   javac -d out model/*.java exception/*.java persistence/*.java controller/*.java view/*.java Main.java
4. Run:
   java -cp out Main
5. A data/ folder is created automatically on first run — that's where your saved transactions live

---

## Git Discipline Notes
Minimum 10 meaningful commits required.
