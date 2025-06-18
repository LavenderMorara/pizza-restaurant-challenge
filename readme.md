Pizza Restaurant API
A RESTful API for managing restaurants, pizzas, and the prices of specific pizzas at different restaurants.

Setup Instructions
Clone the repository

git clone https://github.com/LavenderMorara/pizza-restaurant-challenge.git
cd pizza-restaurant-api
Create a virtual environment with pipenv

pipenv install
pipenv shell
Install dependencies

pip install Flask flask-migrate flask-sqlalchemy sqlalchemy_serializer
Run the application

flask run
Database Migration & Seeding
Initialize the database

flask db init
Generate migration scripts

flask db migrate -m "Initial migration."
Apply migrations

flask db upgrade
Seed the database

Run the seed.py file:

python seed.py
Routes Summary
Method	Endpoint	Description
GET	/restaurants	List all restaurants
GET	/restaurants/<id>	Get details of one restaurant with pizzas
DELETE	/restaurants/<id>	Delete a restaurant
GET	/pizzas	List all pizzas
POST	/restaurant_pizzas	Create a restaurant-pizza price relationship
Thunder Client Usage
Use Thunder Client (VS Code Extension) to test endpoints:

GET Restaurants

Method: GET
URL: http://localhost:5555/restaurants
GET Restaurant by ID

Method: GET
URL: http://localhost:5555/restaurants/1
POST Restaurant Pizza

Method: POST

URL: http://localhost:5555/restaurant_pizzas

Body (JSON):

{
  "price": 10,
  "pizza_id": 1,
  "restaurant_id": 2
}
DELETE Restaurant

Method: DELETE
URL: http://localhost:5555/restaurants/1
Notes
Use a WSGI server (e.g. Gunicorn) for production.
