# Table of contents
* [Overview](#overview)
* [CartoDB tutorial](#introduction-to-cartodb)

# Your account

http://`LOGIN_NAME`.cartodb.com

# Overview

We'll be using CartoDB to make maps. CartoDB is a platform for making tile-maps, otherwise called slippy maps, which are ones that you can zoom and pan around on.

Maps, generally, can either contain point data, or polygon data. Points would be individual locations such as crime incidents. Polygons are shapes such as states, counties, congressional districts etc. We'll start by looking at and styling some point data. This section is based on a workshop Andrew Hill and Michael Keller gave and for which Andrew made all of the awesome gifs below.

##### Who

* Michael Keller, [@mhkeller](https://twitter.com/mhkeller) - [contact info for questions](http://bit.ly/contact-mhk)

### Bonus

By the end of this workshop you will also have created a map with infowindows and legends and you will have created maps that you can embed and share on your websites or Twitter.

# Introduction to CartoDB

[CartoDB](http://cartodb.com) is an open source tool hosted as an online service. Anyone can create a free account and for those more adventurous, the source is available on [GitHub](http://github.com/CartoDB/CartoDB).

![cartodb_intro](http://csvsoundsystem.github.io/nicar-cartodb-postgis/assets/gifs/cartodb_intro.gif)

#### Tutorials

You can find a long list of tutorials, both written and video, on [the CartoDB website](http://developers.cartodb.com/tutorials.html)

#### Documentation

As you learn more about CartoDB, start digging into the [online documentation](http://developers.cartodb.com/documentation/apis-overview.html)

CartoDB allows you to make more than just maps, it can help you build entire geospatial applications. There is an easy to use [Javascript library](http://developers.cartodb.com/documentation/cartodb-js.html) that you can use to integrate maps, geospatial data, and SQL queries into your website. 

#### Support

As you start expirementing more you'll want to know about the [GIS StackExchange](http://gis.stackexchange.com/questions/tagged/cartodb). If you tag questions with `cartodb`, `postgis` or both you will get great help from the community. Just remember to keep question titles short and descriptive. Same goes for the question content, keep it short and to the point. Include links to code (preferably code that wont disappear in the future) or include portions of relevant code for potential helpers to better understand your problem.


### Using the dashboard

The CartoDB dashboard is broken down into a few different interfaces. 

##### The table manager

This is the first page you see when you load your account. It is where you will drag new files for upload or create new blank tables. You can see and delete existing datasets here.

##### The table view

When you load a new dataset or load an old one, you'll be brought to the table view. The table view lets you look at the ```columns``` and ```rows``` of your data. You can edit individual values. You can change column names and types. You can filter your data and query it using ```SQL```.

##### Map view

From any table, you can click `Map` to see the map of the data. As long as your data contained some geospatial information, it should appear on the map. From here, you can style and edit your geospatial data. It is a good place for prototyping published visualizations.

##### Visualization

Whenever you want to publish a map or combine multiple map layers into a single map to be published, you'll create what is called a ```Visualization```. Visualizations live above maps and tables. They are linked directly to the data in your tables, but you can change the styles and filters of a visualization as much as you like. Visualizations do not take up more space on your account. So from one dataset, you can publish many visualizations.

##### Visualization manager

Just like your table manager, there is a page for you to see all your visualizations. You can also delete visualizations. Deleting a visualization will not remove the underlying table or map. 

### Importing data

Importing data into CartoDB is easy! All you need is a file in a supported format (CSV, KML, GeoJSON, and Shapefile are all good ones) either online or on your desktop. You can drag local files right to your browser to import. Remote files you can import by pasting the URL into the import field.

#### Datasets

| File          | Dataset name     | Geom type |
| ------------- |:----------------:|:---------:|
| [counties_ne.zip](http://csvsoundsystem.github.io/nicar-cartodb-postgis/data/counties_ne.zip) | Nebraska Counties   | polygons |
| [postoffices_ne.zip](http://csvsoundsystem.github.io/nicar-cartodb-postgis/data/postoffices_ne.zip) | US Post Offices | points |

##### Four ways to get data into CartoDB

1. Drag and drop a file or a ZIP to you dashboard
2. Import from a URL
3. Add new data to a row in your tables or by drawing on the map
4. Use authenticated [SQL API](http://developers.cartodb.com/documentation/sql-api.html) calls to write data

![import](http://csvsoundsystem.github.io/nicar-cartodb-postgis/assets/gifs/import.gif)

#### First data import

Let's start by importing the dataset of Nebraska Counties.

1. Right click the [counties_ne.zip link](http://csvsoundsystem.github.io/nicar-cartodb-postgis/data/counties_ne.zip), copy URL to clipboard
2. Go to your CartoDB dasboard in the table manager
3. Click ```New table```
4. Paste the data URL into the form field
5. Click ```Create table```

## Creating maps

### Basic map styling

##### Choropleths, Category maps, Bubble maps

![styling](http://csvsoundsystem.github.io/nicar-cartodb-postgis/assets/gifs/styling.gif)

There are many styles possible in CartoDB. The tool includes a simple style wizard for you to apply and customize just some of these. When you grow out of the wizard, you'll want to dig into the CSS editor to really customize your maps.

##### Infowindows and legends

You can add infowindows and legends to any maps you create. There are some nice simple tools for you to create and customize. As you learn more though, you can also take advantage of full HTML templating to make them look and behave exactly as you want.

![infowindows and legends](http://csvsoundsystem.github.io/nicar-cartodb-postgis/assets/gifs/legends.gif)

### Visualizations

Let's start by importing the second dataset of Nebraska Post Offices. Go back to your table manager, then

1. Right click the [postoffices_ne.zip link](http://csvsoundsystem.github.io/nicar-cartodb-postgis/data/postoffices_ne.zip), copy URL to clipboard
2. Go to your CartoDB dasboard in the table manager
3. Click ```New table```
4. Paste the data URL into the form field
5. Click ```Create table```

Now that we have our Post Office dataset, let's create a visualization. You do this by clicking the ```VISUALIZE``` button in the upper right. Next, give your visualization a name. This will take you to a new visualization where you can publish you can finalize design, add new layers, or publish your map.

### Combine layers

Visualizations allow you to mix multiple datasets into a layered map. You can add a new layer by clicking the plus sign directly above the right-hand menu.

![infowindows and legends](http://csvsoundsystem.github.io/nicar-cartodb-postgis/assets/gifs/layers.gif)

You can reorder the layers on the map by dragging layers up through the stack. Each layer can be styled and edited independantly. You can also add interactivity and legends for the layers. 

### Publish maps

Right away you can get a public link for your visualization. Where the button ```VISUALIZE``` used to be, it should new say ```PUBLISH```. From there you can get the menu for publishing maps.

![infowindows and legends](http://csvsoundsystem.github.io/nicar-cartodb-postgis/assets/gifs/visualize.gif)

##### Links, embeds, CartoDB.js

Publishing maps can be as simple as getting the sharable URL. The interface also gives you an ```embed``` option for adding maps to your blog or website. It also has an ```API``` option, for using your visualization with our [CartoDB.js](http://developers.cartodb.com/documentation/cartodb-js.html) library. CartoDB.js will allow you to integrate highly customized maps directly into your website. For now, sharable URLs and map embeds should get you pretty far.

# Bonus example

### Styling points

#### Download the data

| File          | Dataset name     | Geom type |
| ------------- |:----------------:|:---------:|
| [unconventional_wells_dummy.zip](http://csvsoundsystem.github.io/multimedia-workshop/data/unconventional_wells_dummy.zip) | Oil wells in PA (dummy data)  | polygons |

#### Experiment

Style this data according to its different attributes. Play around with bubble maps, torque animation and coloring by year to see trends. 
