
# SpotiFinder


# Project Details
Our program is divided into multiple directories that deals with different aspects of our project. Our auth directory stores components for authorization, with Spotifinder dealing with our main homepage and components for our Search and Merge features. Styles packages includes all of our frontend css styling. Images contains our picture for our logo and icons for our navbar, and utils contains files necessary to communicate with our backend server and the authentication process for both Google and Spotify. 

Our server deals with our backend processes for both our Merge and Search features and deals with making API calls to obtain artist and song data from the Spotify database, along with performing the calculations when determining similar artists or merging artists. 

When our server is first initialized, it will assign the handlers to each path via spark. 

## Component Design

The project in discussion is a user input interface built with an integrated backend to handle user search requests given by users from the front end. This application is designed with an intuitive user interface to visualize interactive results using the Spotify embedded player. 

1.  Search
    This component is responsible for our popularity search, which allows users to search for similar artists based on a popularity measurement.Command Execution: A mechanism to execute commands based on user input, utilizing the command registry for lookup and dispatch. 

2.  Google and Spotify Authentication
    We have implemented a robust and secure login system for our Spotifinder project leveraging Google and Spotify's authentication process through Firebase and window references. By integrating Firebase authentication, we ensure that only authorized users can access their Spotify or Google accounts and perform searches and add songs.

3.  API fetching and broadband
    We've developed a versatile utils directory with api, cookie, and overlay components tailored to retrieve JSON data from our dedicated backend server and to store user searches and return results.

4.  Backend Handlers
    We've implemented handlers for communication between frontend query calls from the user and server JSON data, which includes handlers for our MergeArtists and SpotifyRelatedArtists. This includes the backend server calculation for finding related artists and also merging two artists, which are done through a set of algorithms derived from machine learning, including data normalization and Euclidean distance calculation to find similar artists. 



## Team members 

The team was Jowet Haile (jehaile), Anna Luiza Sant'Anna Arantes, Jimin Ryu (jlryu), and SaNyah Hunter. 

## Estimated total time

About 50 hours between implementation, testing, and documentation

## Repo Link
https://github.com/cs0320-s24/term-project-spotifinder.git

# Design Choices
We were inspired my Spotify's aesthetic when designing our application. So we tried to simulate spotify's dark colors, green logo with a fun custom Spotifinder logo we created by putting the green spotify logo into a magnifying glass with a tie-die splash background! We did a similar color design for our merge logo. You can easily switch pages using our sidebar. We also added a sign in component to allow a user to connect with their Google or Spotify account. This feature could be useful for future development, perhaps for a saved songs/artist page or to curate the search results into a spotify playlist. Our main page allows a user to enter a name, interact with our slider to pick a popularity score then hit submit. Upon submission the user will get 3 artist results and 3 songs by that artist organized by columns. We felt like this design would allow users to receive multiple options of new music and allow the user to play the songs using our embedded player. The popularity slider only goes down to 60 because of the way Spotify's API is set up it does not have many accurate / relevant results. Our merge page allows a user to enter two artist names and then return a similar artist between themby taking the average value of all the components so danceability acousticness loudness tempo etc.


# Errors/Bugs
There are no bugs in the code impacting the functionality of our program significantly. However, when searching for related artists with less known artists depending on the data in Spotify's API our algorithms may not return differing results for a variety of popularity scores for that artist because of the lack of data. Similarly, some artist may not have related artists at a specific popularity score, you may have to try a few numbers above or below. Lastly, our merge page only computes related artists between the two based on the top 160 artists on Spotify, due to the large amount of API calls that searching between more would cause. We can definitely save more artists though to make our database bigger!


# Tests
The test suite additionally includes backend unit tests such as Merge Artists and finding related artist features, in addition to creating mock http requests using Mockito to ensure our program successfully handles requests and responses from the Spotify API. 


# How to
To start the backend cd into the backend directory. Enter the commmand mvn package in the terminal and then ./run or . To start the front end, cd into the client directory. Run the command npm install followed by npm start. 

# Collaboration
Spotify API, Embedded Player API
