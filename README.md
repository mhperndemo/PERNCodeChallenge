Here is a list of endpoints that should be supported to make the front end work.  Please implement at least 3 of them.  (if you choose not to implement login/logout, please at least stub them out or the UI will not work)

Please implement a SQL database of some kind to store the data.


- POST /user/login
- logs the user in 
- body: {
    "username":"test@example.org",
    "password":"password",
    "remember":true
  }
- response schema:
  {
    "user_id":2,
    "name":"test user",
    "email":"test@example.org",
    "phone":null,
    "roles":[null]
  }

- GET /user/logout
- logs the current user out
- response schema: "Created"

- GET /movies
- returns a list of all movies (would be helpful to seed the database with some movies, the UI for adding movies isn't functional)
- response schema:
  [
    {
      movie_id": "1",
      title": "Oceans 11",
      rating_classification": "PG-13",
      description": null,
      release_date: "2001-12-07T00:00:00.000Z",
      created_at: "2020-06-13T04:16:14.813Z",
      updated_at: "2020-06-13T04:16:14.813Z",
      runtime": {
        hours: "1",
        minutes: "56"
      },
      avg_rating: "'3.5"
    }
  ]

- POST '/movies'
- body: {
    title": "Oceans 11",
    rating_classification": "PG-13",
    description": "A great heist movie",
    release_date: "2001-12-07T00:00:00.000Z",
  }
- inserts a new movie to the movie collection

- GET '/movies/:movie_id'
- param: movie_id
- gets details about a particular movie
- response schema:
  {
  	movie_id": "1",
  	title": "Oceans 11",
  	rating_classification": "PG-13",
  	description": null,
  	release_date: "2001-12-07T00:00:00.000Z",
  	created_at: "2020-06-13T04:16:14.813Z",
  	updated_at: "2020-06-13T04:16:14.813Z",
  	runtime": {
    	hours: "1",
    	minutes: "56"
  	},
  	avg_rating: "'3.5"
  }

- GET '/people'
- returns a list of all people (actors)
- response schema:  
  [
    {
      "person_id": 13,
      "name": "Brad Pitt",
      "location": null,
      "born": "1963-12-18T00:00:00.000Z",
      "died": null,
      "description": "An actor and producer known as much for his versatility as he is for his handsome face",
      "thumbnail_asset": null
    },
    ...
  ]

- GET '/people/:person_id'
- param: person_id
- returns details about this person, including a list of all the roles this person has had
- response schema:  
  { 
    roles:[
      {
        "movie_id": 1,
        "title": "Oceans 11",
        "release_date": "2001-12-07T00:00:00.000Z"
      },
      ...
    ],
    "person_id": 13,
    "name": "Brad Pitt",
    "location": null,
    "born": "1963-12-18T00:00:00.000Z",
    "died": null,
    "description": "An actor and producer known as much for his versatility as he is for his handsome face"
  }


