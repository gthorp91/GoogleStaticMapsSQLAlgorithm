# GoogleStaticMapsSQLAlgorithm
Google Static Maps API Polyline Encoding Algorithm within SQL, plus extra features to enable dynamic static maps with custom polylines easily mapped with Long/Lat coordinates of UK Postcodes


The following SQL procedures have been tested and run correctly on a Sybase 16 sever as stored procedures, being used and called by a SAP Crystal Report to return a HD Static Map picture, based solely on free ONS Postcode and Long/Lat data.

The following Procedures/Functions have been completed so far as part of this project:
 
1.  Integer to Binary (varchar)
 
2.  Binary (varchar) to Decimal
 
3.  MAIN - (Lat,Long) to Encoded ASCII String (varchar)

4.  Circle PolyLine generator; this uses the point from the above to encode a PolyLine with 36 points (appears almost circular) on the static map to show an area of any distance in Kilometers. 

5.  Zoom; to allow the PolyLine to be shown at its best possible zoom rate on the map.

5.  Coordinate list; Can be used to mark other addresses/locations on the map as well as the main point, other table(s) with links to the main address need to be created for this to function correctly. 

All that is needed from a table(s) currently is:
Trimmed Post Code (UK) in format XX999XX
Lat Column with the correct Latitude decimal (5,6)
Lon Column with the correct Longitude decimal (5,6)
 
 # Altnernativley, just the Lat/Long of any point can be provided directly to the main procedure which will output the ASCII string. This string needs to simply be appended to the following URL:
 
http://maps.google.com/maps/api/staticmap?center=
{Lat},{Lon}
&scale=2&zoom=
{Zoom}
&size=1000x1000&style=feature:poi|visibility:off&path=fillcolor:0x00FF0033|color:0x00FF00|enc:
{ASCII String}
&maptype=hybrid&markers=size:small|color:blue|
{Lat},{Lon}



 
 
