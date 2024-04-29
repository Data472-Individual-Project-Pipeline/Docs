# Data Collection Protocol

For the ingestion endpoint, 
your data will be collected in json format.

The main set of data (dimensional types) will be as clean as possible with links to the metadata and groupid.

The following fields are necessary for identifying your dataset.
Example dataset
uid	dimension	obs_value	unit	metaid
GCW	Time	    10:30:00pm	NA	    10
GCW	Spacial	`-70.322, 10.22 NA	    10
GCW	Geo	        30	        m/s	    10


# Required Fields
- Unique ID (uid)
The unique ID should be something you will always use to identify your project name.

- Dimension (GEO, Date, Time, Spacial, etc) 
The dimension type explains to our API how it should treat your data so make sure to be specific,
We can ratify more fields if they are necessary but we don't want multiple fields i.e Geo Geodata Geospatial
or Time TimeData Times, this increases our processing time and also would be difficult.

- Observation value
This can be a set of items i.e longitude and latitude
or a single item. 
You can delimit multiple items with a comma or a space we will treat spaces as if it is a new set of data.
Attach explanatory notes to the metadata if you think there needs to be a clearer explanation on how we should treat your dataset!

- measurement unit (or NA if not applicable)
This tells us what unit to expect your value to be in, note Geo and Time is N/A as an example of N/A.
But if your time data is a specific set of format a good example is 'hh:mm:ss' we will try to wrangle your data based
on good known date converters.

- metaid
The metaid is very important,
your metaid is a single value that tells us whether your data is related or not, 
for example metaid 10 tells us that your data is GCW and relevant notes are in the metaID 10 field.



Metadata.
Metadata can include as many fields as you need but for metadata it is best that it is information
only relevant to that dataset

For example the Time dataset will have only time related data and the metadata for time will contain many more fields of data. 
This helps keep the data uniform to what each dataset needs and ensures additional information that is not relevant to all other data is
kept separate but has a link back using a metaid.

you can have as many fields as you want.

