# Dice Game (WIP - details subject to change)

A simple single-page dice game that can be played either against an AI without requiring an account, or against a second player online by using an account.

I've been learning the T3-stack (typescript, tailwind, tRPC, Next.js, NextAuth) and I wanted to use what I've learnt in a new project. 

The dice game was a fun little idea that has the right level of complexity to make for a good portfolio project, and by having a 2 player online mode it means it can be a full-stack app as well.

The dice game itself originates from an existing video game "Cult of the Lamb" and is not my own creation. This project was just to have fun creating the logic for that game.

The AI for single player mode is simple to start with but once the app is complete the idea is to learn how machine learning works and then apply it to the game AI here.

This app uses React and tailwind for the frontend and NodeJS, tRPC, and prisma for the backend, using typescript throughout for type-safety.

## Installation (WIP - Follow steps 1-3 which are currently accurate, steps 4-7 are currently inaccurate but will become accurate at a later date)

1. ```git clone``` to your machine
2. Install project dependencies (```npm ci```, or your package manager of choice)
3. Add a ```.env``` file ensuring ```.env``` is included in your ```.gitignore```
4. Add ```DATABASE_URL``` and ```SHADOW_DATABASE_URL``` variables to your .env adding database url's for each for prisma to use. Add ```?schema=prisma``` to the end of the first and ```?schema=shadow``` to the end of the shadow database url
5. Add ```JWT_SECRET``` and ```JWT_EXPIRY``` variables to your ```.env``` providing a token secret for the former and a duration before the token expires for the latter
6. Add ```REACT_APP_API_URL``` and ```REACT_APP_USER_TOKEN``` variables to your ```.env``` providing an api url and a string for your token to be referenced by
7. Run ```npx prisma migrate reset``` to execute the existing prisma migrations 

## Usage

### Homepage

- Whole left side of the screen is clickable and doing so will bring the user to a game against an AI without requiring the creation of an account
- Whole right side of the screen is clickable and doing so will bring the user to a simple sign up/login page, once logged in the user will be brought to a 2 player game page (if the user has a token clicking the right side will take them right to the game)
  
### Game (Vs AI)

- The page will display two 9x9 grids with the names "player 1" and "AI" besides each respective grid, the score for each player is below their names
- A summary of the rules is provided on the top-right of the page
- On the bottom-right is a clickable dice, doing so will roll the dice, once it lands on a number the player is able to drag the dice to the column of their grid they wish to add it to
- As dice are added to the grids the scores update
- Once either the player's or the AI's grid is full the game ends and a message displayed naming the winner and explaing that the game session will end shortly
- Once the session ends the player will be brought back to the home page

### Game (Vs a second player online)

- The page will appear the same as the page vs an AI however with the names of the players changed to the players usernames
- The page is uninteractive and a message displays saying "waiting for player 2" until they join the game
- Once the second player has joined the first player is able to click on the dice to start the game
- The players are able to take it in turns clicking the dice and are unable to do so when it is the other players turn
- Once a player's grid is full and the game ends a message is displayed naming the winner and explaing that the game session will end shortly
- Once the session ends an api call will be made to have the game deleted from the database (with the game complete the data is no longer required and is removed)

## Development Process (Currently WIP)

Having thought to do this project for fun, to test out the new tech I've learnt, and to create a good project for my portfolio I began planning out what would be required to create the app

The image below shows the wireframes and ERD I created to give myself something to work off when initially building the frontend and backend

![ERD and Wireframes](/assets/dice-game-ERD-&-Wireframes.png)

## Feature changes/additions (Currently WIP)

1. Currently in it's infancy and being worked on to first reach a MVP stage
2. Once complete the plan is to learn how machine learning works and apply it to the AI in this app
