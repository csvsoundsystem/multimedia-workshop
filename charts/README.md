Charts
===

Charts are an often used and often abused element of visual presentation. 

In general, charts should remove all extraneous information. Here's an example: <http://darkhorseanalytics.com/blog/data-looks-better-naked/>

#### Highcharts

We're going to use the Highcharts library since it's free and has a lot of good features. Let's takea look at their demos: <http://www.highcharts.com/demo>

# What is data?

### Excel or CSV format

Data is most friendly in a regular spreadsheet format. Spreadsheets aren't always regular, however. Sometimes they come with extraneous headers or odd formatting. There is no one-ideal format, since that will depend on your data. But usually, spreadsheets that have the same structure for every row are well-formatted.

A CSV or comma-separated value format file is a common spreadsheet format. Think of it as the generic version of a drug versus Excel which is the brand name version. You'll want to save you Excel files as CSVs to use them on the web.

### JSON

JavaScript and other scripting languages usually read data in CSV format and convert them into a format they understand better called JSON or JavaScript Object Notation. We'll briefly go over what it looks like since Highcharts' configuration is in JSON.

Let's say you have a spreadsheet that looks like this

| Name          | Party    | Donation amount |
| ------------- |:----------------:|:---------:|
| Pierre | Democrat | 500 |
| Lucy | Democrat | 200 |
| Alfred | Republican | 700 |

In JSON that would look like this

````
[
	{
		"Name": "Pierre",
		"Party": "Democrat",
		"Donation amount": 500
	},
	{
		"Name": "Lucy",
		"Party": "Republican",
		"Donation amount": 200
	},
	{
		"Name": "Alfred",
		"Party": "Democrat",
		"Donation amount": 700
	}
]
````

Notice how we have a row object that repeats three times and is separated by commas. Also, each element is followed by a comma except for the last item in each object. Each row object is in between `{ }` and the whole list is in `[ ]`. Curly braces, `{ }` designate objects and hard brackets `[ ]` define a list of objects, separated by commas.

Also, notice how text is in quotes while numbers are not. If you put numbers in quotes they would be treated as text.

That's what a csv looks like in JSON but JSON is a very flexible format, so you can really have any number of lists and objects.

Here is a single object that contains other objects and a list of colors:

````
{
	"chart_type": "line",
	"width": 500,
	"height" 200,
	"container": "#chart-container",
	"style": {
		"font": "Helvetica",
		"font-size": "20px",
		"colors": ["red", "orange", "purple"]
	}
}

````

Let's take a look at a simple line chart in Highcharts: <http://jsfiddle.net/gh/get/jquery/1.9.1/highslide-software/highcharts.com/tree/master/samples/highcharts/demo/line-basic/>


# Working with real data

Let's work with some real data on liquid gas production in Pennsylvania from 1981 to 2014: <http://www.eia.gov/dnav/pet/hist/LeafHandler.ashx?n=PET&s=MNGFPP12&f=M>

Click "Download Data (XLS Files)" and open that in Excel.

#### Clean and convert to CSV

As we talked about, this data has extraneous headers, delete those rows.

To convert it to a csv, do "Save as" and select "Comma-separated values" as the file format.

Open up this CSV in Sublime Text 2.

##### Adding data to the chart

Copy the values into the data list and copy the months into the categories list. A great trick to do this is to hold down the option-key and drag.
