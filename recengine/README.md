# Recommendation Engine for Resident Advisor 

**Website:** `http://69.195.124.253/~speakit9/data/`

# php-files:

- Contains the php files which write read/write data to the SQL database and present
the interface to the user. This is stored on my remote server speakinimages.com
- userid.php is the main php file which reads the data from the database and outputs it into tables on the site.
- write_events.php is a php script which writes the data to my SQL database. This program is modified depending on the particular
table and format of the event.


# scraper-programs:

- Contains the program RAEventPageScraper.py which scrape event data listings page on RA. These files are then outputted
into files which are read by event-suggestors/`RA_scrapedoutput_reader.py`

#nearest-neighbors-generators:

Contains `RASparse_rowcol_generator.py` which generates the row/column matrix entries for userid/events. Then `RA_generate_neighbors.py`
uses the output of this file and collaborative filtering to list nearest neighbors of each userid.

# event-suggestors:

- `RA_history_event_suggestions.py` which generates recommendations from reading output of `RA_scrapedoutput_reader.py` and the users
event history (djs, promoters, venues). 
- `RA_scrapedoutput_reader.py` reads the raw output from `RAEventPageScraper.py` and generates a listing of each user/event with the djs/promoters outputed
on one line.
- `RA_neighbors_event_suggestions.py` generates event suggestions from finding events that the nearest neighbors found in `RA_generate_neighbors.py` produced
and listing them (up to a maximum of 10).
