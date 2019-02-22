# LIRI Bot

### Overview

LIRI is like iPhone's SIRI. However, while SIRI is a Speech Interpretation and Recognition Interface, LIRI is a _Language_ Interpretation and Recognition Interface. LIRI is a command line node app that takes in parameters and gives you back data.

### Video Snapshot

![Gif of Demo](https://github.com/furiameyer/liri-node-app/blob/master/Feb%2022%202019%205_35%20PM.gif)

For a full resolution video of the demo click [here](https://drive.google.com/file/d/1AHV7Bgnsnrn0wZf-B1a5Z2S1igVqYSRv/view)


### Node Packages used in the App

   * [Node-Spotify-API](https://www.npmjs.com/package/node-spotify-api)
   
        * You will need a Spotify ID and Secret to run the app on your computer; to get one of your own, click [here](https://developer.spotify.com/my-applications/#!/)

   * [Axios](https://www.npmjs.com/package/axios)

     * Axios is used to grab data from the [OMDB API](http://www.omdbapi.com) and the [Bands In Town API](http://www.artists.bandsintown.com/bandsintown-api)

   * [Moment](https://www.npmjs.com/package/moment)

   * [DotEnv](https://www.npmjs.com/package/dotenv)
   
   * [fs](https://www.npmjs.com/package/fs)
   
## Features of LIRI

### What Each Command Does

1. `node liri.js concert-this <artist/band name here>`

   * This searches the Bands in Town Artist Events API (`"https://rest.bandsintown.com/artists/" + artist + "/events?app_id=codingbootcamp"`) for an artist and renders the following information about each event to the terminal:

     * Name of the venue

     * Venue location

     * Date of the Event

2. `node liri.js spotify-this-song '<song name here>'`

   * This shows the following information about the song in your terminal/bash window

     * Artist(s)

     * The song's name

     * A preview link of the song from Spotify

     * The album that the song is from

   * If no song is provided then LIRI will default to "The Sign" by Ace of Base.

   * LIRI utilizes the [node-spotify-api](https://www.npmjs.com/package/node-spotify-api) package in order to retrieve song information from the Spotify API.

3. `node liri.js movie-this '<movie name here>'`

   * This will output the following information to your terminal/bash window:

     ```
       * Title of the movie.
       * Year the movie came out.
       * IMDB Rating of the movie.
       * Rotten Tomatoes Rating of the movie.
       * Country where the movie was produced.
       * Language of the movie.
       * Plot of the movie.
       * Actors in the movie.
     ```

   * If the user doesn't type a movie in, the program will output data for the movie 'Mr. Nobody.'

   * LIRI uses the `axios` package to retrieve data from the OMDB API.

4. `node liri.js do-what-it-says`

   * Using the `fs` Node package, LIRI takes the text inside of random.txt and then uses it to call one of LIRI's commands.

     * It runs `spotify-this-song` for "I Want it That Way," as follows the text in `random.txt`.

     * Edit the text in random.txt to test out the feature for movie-this and concert-this.

### BONUS FEATURE

* In addition to logging the data to your terminal/bash window, LIRI outputs the data to a .txt file called `log.txt`.
