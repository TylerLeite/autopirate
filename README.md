# Autopirate
###### "Please don't sue me"
Autopirate looks through your spotify library and downloads all of the songs in there from youtube.
###### "For real tho, please don't sue me"

## Usage

#### Step 1: Install dependencies

* `apt-get install libcurl-dev`
* `pip install pycurl`
* `pip install ytdl`
* `pip install spodipy`

#### Step 2: Create a spotify api application
<b>Important:</b> Make sure you create this under the account you want to download from (you can't currently download other people's playlists) Also, make sure you use `http://localhost:8888/callback` as your redirect url (don't worry, you don't need to actually set up a local server)

I am not going to go into how to do this here since there is a ton of documentation here: https://developer.spotify.com/web-api/tutorial/

#### Step 3: Install Autopirate
`git clone https://github.com/TylerLeite/autopirate.git`

#### Step 4: Config Autopirate
In this step, you must edit pirate.conf. Make sure there are no spaces around the `:` characters
* Change verbose if you want more / less output. 20 gives slightly more, 0 gives much less, -1 gives (almost) none
* Paste your Spotify username, client_secret, and client_id

#### Step 5: Run
* `cd autopirate`
* `python main.py`

Autopirate supports 4 download modes:
* Download all public playlists `python pirate.py -m=apl` (this is also the default)
* Download a specific public playlist `python pirate.py -m=pl -p=YOUR PLAYLIST NAME`
* Download all saved music `python pirate.py -m=s`
* Download all saved music and all public playlists `python pirate.py -m=e`

<b>Note:</b> You may get some weird output in the terminal telling you something about not being able to redirect from console, just click the link in your terminal. This should open up a browser window. Let it redirect and then copy the new url and paste it into the terminal.

<b>Also Note:</b> If there are songs that are in multiple playlists which are downloaded, they will be downloaded multiple times. The exception is if you download saved songs AND all playlists, it will only download saved songs that aren't in a playlist.

<b>Also Also Note:</b> Secret playlists will be SKIPPED
