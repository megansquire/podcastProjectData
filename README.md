# Podcast Project Data

## Citation
Please cite this work as follows:

Megan Squire and Hannah Gais (2021). [Inside the Far-right Podcast Ecosystem](https://www.splcenter.org/hatewatch/2021/09/29/inside-far-right-podcast-ecosystem-part-1-building-network-hate). Southern Poverty Law Center Techwatch. September 30.

Included in this collection are the following files:
* data/shows.csv
* data/episodeMetadata.csv
* data/episodeSegments.csv
* data/cast.csv
* data/episodeCast.csv

## shows.csv
This is the list of shows included in this dataset. 

#### Columns
* showCode - short name for this show (tds, nf, tpc, etc)
* showName
* network - trs, id, other

## episodeMetadata.csv
This is a list of facts about each episode.

#### Columns
* episodeSeqNum - unique number I gave to each episode (primary key)
* podcastSeries - the show code for this episode (maps to shows.showCode)
* episodeNum - this is the number given by the hosts for this episode (nullable)
* airDate - approximate airdate or post date (nullable)
* url - where I found this show or the metadata about this show originally (nullable)
* episodeTitle - title as given by the hosts (nullable)
* episodeSummary - summary of the show as given by the show hosts
* audioUrl - URL where I found the audio recording (nullable)
* frameRateHz - frame rate of this recording (nullable)
* numChannels - number of channels in the audio file (nullable)
* durationSecs - how long is the audio file in seconds (nullable)
* notes - my notes on this episode (nullable)

## episodeSegments.csv
This is a list of all the segments present in each episode that lists segments. A segment is a recurring or one-time portion of the show. Often, timestamps are given for the segments to assist listeners with finding the portion of the show they are interesting in listening to.

#### Columns
* episodeSeqNum - maps to episodeMetadata.episodeSeqNum (primary key)
* segmentNum - number for this segment in this episode (primary key)
* segmentStart - timestamp for when the segment starts within this episode
* segmentDesc - description of the segment, as given by the hosts

## cast.csv
This is a list of all cast members.

#### Columns
* castID - unique number for each cast member (primary key)
* castName - most common name used for this cast member or sometimes real name if documented
* primaryShowCode - show they are most associated with (based on number of appearances), maps to shows.showCode
* aka - other name(s) this cast member may go by
* notes - why this person might be notable, if any 

## episodeCast.csv
This is a list of the cast members appearing on each episode.

#### Columns
* episodeSeqNum - maps to episodeMetadata.episodeSeqNum (primary key)
* castID - maps to cast.castID (primary key)
* role - describes the role of this cast member on this episode (host, guest, etc)
* notes - my notes
