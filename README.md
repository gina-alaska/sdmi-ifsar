GINA SDMI IFSAR
===============

The shapefiles to help GINA keep track of the status
of the IFSAR collections in the state of Alaska.  Check out the project website at [http://alaskamapped.org/dem](http://alaskamapped.org/dem) for details on this project.

![current status map](./maps/Alaska-IFSAR-STATUS-current-thumb.jpg "Current Status")

[full resolution status map](maps/Alaska-IFSAR-STATUS-current.png)

There are currently three major buckets of data tracked here:

Legacy IFSAR
------------

IFSAR flown and collected by Intermap in the early years.  All of
this data was uplifted to public domain for the 2010 IFSAR collection.

2010 IFSAR Collection
---------------------

Interior of Alaska IFSAR collection split between two Fugro Earth Data 
and Intermap.  Majority of that collection has been purchased and delivered.

Legacy shapefile is found in: layers/legacy

2012 IFSAR Collection
---------------------

Flown but not yet fully delivered to the USGS or State of Alaska.

Using this repository
---------------------

You can grab a copy of the latest version of this repository at:
https://github.com/gina-alaska/sdmi-ifsar/archive/master.zip

Take a look in the:

layers/general/SDMI-IFSAR-STATUS

This shapefile is my attempt at organizing the status of all of 
the new SDMI IFSAR collections. 

You will need to use the 'year' attribute to determine what coverage 
is available.  The 2010 collection is all available right now and 
the 2012 collection will be available at the end of this year.

The 'status' attribute is the primary flag being used by GINA to track where
a geocell is towards goal of statewide IFSAR coverage:
  * nil - no status / not collected
  * CAN - spec collected but not yet purchased for processing or delivery
  * SOA - Delivered to the State of Alaska
  * PART - need to sanity check this bucket -- probably: "partial geocell purchase"


Downloading geocells:
---------------------

The 2010 IFSAR cells have 3 additional attributes populated DTM, DSM, and ORI.  Each 
has the URL to the directory with the tar ball and MD5 checksum for that geocell.  

For example:
The N61W147 geocell has the following URL in the DSM attribute:
http://ifsar.gina.alaska.edu/data/2010/DSM/IFSAR.SDMI.2010.FUGRO.DSM_N61W147/

  IFSAR.SDMI.2010.FUGRO.DSM\_N61W147.tar.gz
  IFSAR.SDMI.2010.FUGRO.DSM\_N61W147.tar.gz.md5

This means you can grab a geocell using the following structure using three variables:

  ${URL}/IFSAR.SDMI.2010.FUGRO.${TYPE}_${GEOCELL}.tar.gz
  ${URL}/IFSAR.SDMI.2010.FUGRO.${TYPE}_${GEOCELL}.tar.gz.md5

Test the downloads using:

  md5sum -c *.md5

Questions?
----------

email: support@gina.alaska.edu
