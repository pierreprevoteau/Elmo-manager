# Elmo-manager

## Database
  - Clients(SQL-LONG-CACHE-90-AFTERSAVE) : title, first_name, last_name, email, provider, uid, ibeacon_id, alt_ibeacon_id, style_1, style_2, style_3, style_4
  - Users(SQL-NOCACHE) : provider, uid, last_vote_id
  - History(SQL-SHORT-CACHE-15-NOSAVE) : client_id, song_id
  - Votes(NOSQL?) : client_id, song_1_id, song_2_id, song_3_id, song_4_id, song_1_vote, song_2_vote, song_3_vote, song_4_vote
  - Songs(SQL-MEDIUM-CACHE-15-NOSAVE) : song_id, client_id, category, voted 
  - Settings(SQL-LONG-CACHE-90-AFTERSAVE) : client_id, key, value

## Jobs
  - add_vote(client_id, song_id) Add a +1 for the voted song
  - random_primary_vote(client_id) Add a +1 vote to a random song to prevent a null vote
  - queue_song(client_id, song_id) Add the voted song to the bottom of the Elmo-live playlist
  - add_song(song_id, category) Add a song from a user to the DB
  - sniff_playlist_content(client_id, spotify_user_id, spotify_playlist_id) Add all songs from a playlist to the DB
  - stock_playlist_watcher(client_id) Watch for new songs added or deleted songs to the Elmo-stock playlist and add or remove them to/from the DB

## Settings
  - random_mode : discovery, popular, random, spotify (less voted from db are played, most voted from db are played, thruly random from db, based on spotify recomandation)
  - new_song_mode : open, checked, close (user can add a song, user can add a song but must be validate by admin, only admin can add a song)
  - playlist_live_id : id of the live playlist 
  - playlist_stock_id : id of the stock playlist 

## Spotify playlist
  - Elmo-live (currently played and voted)
  - Elmo-stock (copy of the Elmo DB, add new song to it also add it to db)

## Idea
  - Send notification for Happy-Hour ? 
  - More than 4 style ? Maybe picked randomly ? More than 4 vote ?
  - Placebo mode : Users can't see vote-stats when they vote ?
