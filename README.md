# Bot for finding restaurants in BCN

This is a project where we design, using python language, a telegram bot, where we can find for restaurants with specific attributes and see the shortest path from where we are to the location of a specific one.

## Description of the project

This project is made of four modules in total:

### Restaurant

In this python file we read data from https://opendata-ajuntament.barcelona.cat/, the list of restaurants in Barcelona city. We use pandas to make a dataframe of that and then we store it in a more manageable way. 

It also provides a search function, that is the one we use in order to find restaurant that matches with a query. 

### Metro

In this python file we read also from open data of Barcelona, in this case the metro stations of the city, and we make a grpah with them and their relevant information. At the end of the process, we are also able to see a picture of the metro of Barcelona seen as a graph, without and with the city placed behind it. 

### City

In this python file we obtain a graph wich represents the city of Barcelona, and information about distance and more. We save that a graph and create a new one, combining the metro one with this, and therefore obtaining a representation of the possible locations in barcelona and what are the possible paths to go from one place to another, having information about the time it would cost and thus being able to call an optimization function which an gives the path we should take. We can also obtain a picture of the resultant graph, also with and without the barcelona map at the back of it, and we can aslo show in a map a particular chosen path.

### Bot

In this python file we implement the bot, the gadget that it will be visible to the user. This bot comes with a series a options that are (a part of the obvious /start): 
* /help command: it shows the other options
* /author command: it prints the name of the author of the project (Jordi Baroja)
* /find <query> command: you can type, for example, /find Hamburguesa, and it will print a list of up to 12 possibilities of restaurants where have Hamburguesa as a part of their description. You are, of course, allowed to do some typing mistakes, for example you can type /find piza and it won't be a problem
* /info <number> command: once you have a list of possibilities, use this command to see a brief description (mostly the location) of some restaurant.
* /guide <number> command: this for seeing the best way to go from where the user is to a selected restaurant. Of course it will ask for the location in order to do that. 
  
## Need to install
  
If someone wants to run this project on their PC, it will need to have installed some modules tht allow to run some necessary functions:
  
* Typing extensions: you can install it with "pip install typing-extensions", "pip3 install typing-extensions" or “python -m pip install typing-extensions“. This is to make the TypeAlias, useful for naming your own objects in a more readable way.
* Osmnx: the same as before, just type omnx instead of typing-extensions. This is to get the barcelona graph.
* Networkx: this is to create graph objects, useful when they are big nd linked to information (as distance or colour).
* Static map (pip install staticmap): this is to make plots of the graphs.
* Pillow (pip install pillow): necessary to have networkx package.
* Requests (pip install requests): necessary to have networkx package.
* Haversine (pip install haversine): this is used to calculate distance when we have the coordinates of some place on Earth.
* Fuzzysearch (pip install fuzzysearch): this is used to earch restaurants when and allowing the word to have typing errors.
 
 We need to use the command $ conda activate ox in the directory we are going to run the script, to activate conda environment.
