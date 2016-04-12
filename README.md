# Elmo-manager
---------------------
## Database
#### Client(SQL) : title, ibeacon_id, style_1, style_2, style_3, style_4
#### History(SQL) : client_id, song_id
#### Vote(NOSQL) : client_id, song_1_id, song_2_id, song_3_id, song_4_id, song_1_vote, song_2_vote, song_3_vote, song_4_vote
#### Random_song(SQL) : song_id, category, voted 
---------------------
## Jobs
### add_vote(client_id,song_id)
### queue_song(client_id,song_id)
### add_random_song(song_id, category)
