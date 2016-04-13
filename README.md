# Elmo-manager

## Database
  - Clients(SQL) : title, first_name, last_name, email, provider, uid, ibeacon_id, alt_ibeacon_id style_1, style_2, style_3, style_4
  - History(SQL-SHORT-CACHE-15) : client_id, song_id
  - Votes(NOSQL?) : client_id, song_1_id, song_2_id, song_3_id, song_4_id, song_1_vote, song_2_vote, song_3_vote, song_4_vote
  - Songs(SQL-MEDIUM-CACHE-15) : song_id, client_id, category, voted 
  - Settings(SQL-LONG-CACHE90) : client_id, key, value

## Jobs
  - add_vote(client_id, song_id) Add a +1 for the voted song
  - queue_song(client_id, song_id) Add the voted song to the bottom of the Elmo-live playlist
  - add_song(song_id, category) Add a song from a user to the DB
  - sniff_playlist_content(client_id, spotify_user_id, spotify_playlist_id) Add all songs from a playlist to the DB
  - stock_playlist_watcher(client_id) Watch for new songs added to the Elmo-stock playlist and add them to the DB

## Settings
  - random_mode : discovery, popular, random, spotify (less voted from db are played, most voted from db are played, thruly random from db, based on spotify recomandation)
  - new_song_mode : open, checked, close (user can add a song, user can add a song but must be validate by admin, only admin can add a song)
  - playlist_live_id : id of the live playlist 
  - playlist_stock_id : id of the stock playlist 

## Spotify playlist
  - Elmo-live (currently played and voted)
  - Elmo-stock (copy of the Elmo DB, add new song to it also add it to db)
