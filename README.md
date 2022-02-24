# Tietokantasovellus - AnimeList

## Project Description
The website is available in [Heroku](https://tsoha-animelist.herokuapp.com/).  
The project is a website where anime are listed and users can search anime, add them to their lists to keep track of what they are watching and what they have watched. This project takes inspiration from [MyAnimeList](https://myanimelist.net).  
Anime data is taken from [here](https://github.com/manami-project/anime-offline-database) and the AGPL-3.0 license is used because of that.

## Features
- `/topanime`
  - Listing all anime and sorting them by their average score
  - Searching anime
  - Searching anime by tag (select a tag from `/anime/<id>` view)
- `/tags`
  - Listing tags to search by
- `/anime/<id>`
  - Viewing more detailed information about a specific anime
- `/login` and `/register`
  - Accounts
- `/list/<username>`
  - Personal anime list
  - Seeing others' lists
- `/profile/<username>`
  - Importing data from MyAnimeList
  - Setting to show hidden anime (There are no hidden anime in Heroku because of database table size restrictions)
  - Statistics of watched anime
  - Seeing others' profiles
- `/related`
  - Seeing related anime that are not on your list

### Features that I might add if I have enough time
- Adding users as friends
- Watch history

## Running project
### Initializing
1. Create a `.env` file at project root and add the following lines to it:
    ```
    SECRET_KEY=<secret_key>
    DATABASE_URL=<postgresql:///user>
    ```
    and replace with corresponding values. SECRET_KEY should be a long random string
2. Create and start virtual environment
   ```
    $ python3 -m venv venv
    $ source venv/bin/activate
    ```
3. Install dependencies
    ```
    $ pip3 install -r requirements.txt
    ```
    If installing requirements fails, try installing alternative requirements
    ```
    $ pip3 install -r requirements-alt.txt
    ```
4. Download 'anime-offline-database-minified.json' from [here](https://github.com/manami-project/anime-offline-database) and place the file at this project's root
5. Initialize the database
   ```
   $ INIT=True flask run
   ```
### Running project
```
$ source venv/bin/activate
$ flask run
```