Maps for UK
===========

Introduction
------------

The maps for the UK were downloaded from the following address: [https://www.ordnancesurvey.co.uk/opendatadownload/products.html][1]

You need to scroll to **Boundary-Line**, tick the download box and scroll to the end, click **Next** and follow the instructions. You will receive a mail with the download link.

Conversion
----------

For the current file I have used the **european_region_region** files from the zip archive. Here are the steps you need to take:

1.  Unzip all the **european_region_region** files.
2.  According to [this blog post][2] the files are in a different format than most maps use, so we need to convert it.
3.  Run the following command to download the **GDAL** (Geospatial Data Abstraction Library) that contains a bunch of useful utilities:

        sudo apt-get install gdal-bin

4.  After this you will have the **ogr2ogr** tool that we will be using later.
5.  Now run the following command to convert the coordinates:

        ogr2ogr -t_srs WGS84 [output_shp_file] [input_shp_file]

6.  Now you can get rid of the old shp files and use only the new ones. After you have your shape files using the right coordinate systems, you can create the **GeoJSON** by running the following:

        ogr2ogr -f GeoJSON [output_json_file] [input_shp_file]

7.  Done!

Conclusion
----------

I am just going to give a number of useful links that I used to get all this information:

*   [http://www.flyingtophat.co.uk/blog/2011/03/26/converting-shapefiles-projection.html][2]
*   [http://blog-en.openalfa.com/how-to-add-interactive-maps-to-a-web-site/][3]


[1]: https://www.ordnancesurvey.co.uk/opendatadownload/products.html
[2]: http://www.flyingtophat.co.uk/blog/2011/03/26/converting-shapefiles-projection.html
[3]: http://blog-en.openalfa.com/how-to-add-interactive-maps-to-a-web-site/