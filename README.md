# Elmo-manager

## Database
#### Users(SQL) : first_name, last_name, email, password, client_id
#### Clients(SQL) : title, ibeacon_id, oauth, style_1, style_2, style_3, style_4
#### History(SQL) : client_id, song_id
#### Vote(NOSQL) : client_id, song_1_id, song_2_id, song_3_id, song_4_id, song_1_vote, song_2_vote, song_3_vote, song_4_vote
#### Song(SQL) : song_id, category, voted 
#### Settings(SQL) : client_id, key, value

## Jobs
#### add_vote(client_id, song_id)
#### queue_song(client_id, song_id)
#### add_random_song(song_id, category)

## Settings
#### random_mode : discovery, popular, random (less voted, most voted or thruly random)
