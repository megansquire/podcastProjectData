# Podcast Project Data

Included in this collection are the following files:
* shows.csv
* episodeMetadata.csv
* episodeSegments.csv
* castMembers.csv
* episodeCast.csv

## shows.csv
This is the list of shows included in this dataset. 

#### Columns
* showCode
* showName
* network

## episodeMetadata.csv
This is a list of facts about each episode.

#### Columns
* episodeSeqNum - unique number I gave to each episode (primary key)
* podcastSeries - the show code for this episode (maps to shows.showCode)
* episodeNum - this is the number given by the hosts for this episode (nullable)
* airDate - approximate airdate for post date (nullable)
* url - where I found this show (nullable)
* episodeTitle - title as given by the hosts (nullable)
* episodeSummary - as given by the show hosts
* audioUrl - URL where I found the audio (nullable)
* frameRateHz - frame rate of this recording (nullable)
* numChannels - number of channels in the audio file (nullable)
* durationSecs - how long is the audio file in seconds (nullable)
* notes - my notes on this episode (nullable)

## episodeSegments.csv
This is a list of all the segments present in each episode that lists segments.

#### Columns
* episodeSeqNum - maps to episodeMetadata.episodeSeqNum (primary key)
* segmentNum - number for this segment in this episode (primary key)
* segmentStart - timestamp for when the segment starts within this episode
* segmentDesc - description of the segment, as given by the hosts

## cast.csv
This is a list of all cast members.

#### Columns
* castID - unique number for each cast member (primary key)
* castName - most common name used for this cast member or sometimes real name if known
* primaryShowCode - maps to shows.showCode
* aka - other name(s) this cast member is "also known as"
* notes - my notes about why this person might be notable, if any 
* gender - gender portrayed by this person in their appearances

## episodeCast.csv
This is a list of the Cast members appearing on each episode.

#### Columns
* episodeSeqNum - maps to episodeMetadata.episodeSeqNum (primary key)
* castID - maps to cast.castID (primary key)
* role - describes the role of this cast member on this episode (host, guest, etc) (nullable)
* notes - my notes (nullable)
