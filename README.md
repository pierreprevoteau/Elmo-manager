# Elmo-manager

## Database
#### Clients(SQL) : title, first_name, last_name, email, provider, uid, ibeacon_id, style_1, style_2, style_3, style_4
#### History(SQL-SHORT-CACHE-15) : client_id, song_id
#### Vote(NOSQL?) : client_id, song_1_id, song_2_id, song_3_id, song_4_id, song_1_vote, song_2_vote, song_3_vote, song_4_vote
#### Song(SQL-MEDIUM-CACHE-15) : song_id, client_id, category, voted 
#### Settings(SQL-LONG-CACHE90) : client_id, key, value

## Jobs
#### add_vote(client_id, song_id)
#### queue_song(client_id, song_id)
#### add_song(song_id, category)
#### copy_playlist_content(client_id, spotify_user_id, spotify_playlist_id)

## Settings
#### random_mode : discovery, popular, random, spotify (less voted from db are played, most voted from db are played, thruly random from db, based on spotify recomandation)
#### new_song_mode : open, checked, close (user can add a song, user can add a song but must be validate by admin, only admin can add a song)

## Spotify playlist
#### Elmo-live (currently played and voted)
#### Elmo-wishlist (when added to this playlist, also added to the Elmo DB)
#### Elmo-database (copy of the Elmo DB)
