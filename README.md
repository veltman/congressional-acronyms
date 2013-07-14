Congressional Acronym Data
======================

This is the data that goes into my [analysis of congressional acronym usage](http://noahveltman.com/acronyms/).  The data comes from [GovTrack](http://govtrack.us/) by way of their [Bulk Data API](http://www.govtrack.us/developers/data).  The files for all bills since 1973 were downloaded in XML format, and bill titles and sponsor information extracted and analyzed.  For details on some of the data complexities to watch out for, see [my notes](http://noahveltman.com/acronyms/#data).

The data consists of four tab-separated files:
* `bills.tsv`.  Basic information about all bills, including bill type, bill number, introduction date, sponsor ID, session of congress, and bill status.  The key columns are `IS_ACRONYM` (boolean, 1 or 0) and `ACRONYM_WORD` (text, contains the acronym word or words).  You can reconstruct a GovTrack URL from the pieces in the format: `http://www.govtrack.us/congress/bills/{session of congress}/{bill type}{bill number}`

* `titles.tsv`.  Titles for each bill, listed by bill ID.  Includes title type ("short","official", or "popular")
* `legislators.tsv`.  Basic information about bill sponsors: name, sortable name, party, GovTrack URL.
* `wordmap.tsv`.  A utility table to deal with the fact that a small number of bills have multiple acronym words.  Some of them are phrases, like "SAFE DOSES"; others have multiple independent acronym titles, like the PACT Act that is also the PRECAUTION Act; a few have a phrase with a non-acronym word in the middle, like "HIRE at HOME".