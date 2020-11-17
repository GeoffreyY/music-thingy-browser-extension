# music-thingy-browser-extension

Warning: this is under active development and most probably will break very frequently.

This is the browser extension for my music database thingy. When listening to music / video on youtube, spotify or other websites (note: to be implmented), you can click on the extension, and extract the information about the song (aka song name, artist name etc) and submit them to the database. You can also tag, rate and comment on the song.

TODO: make extension autoamatically extract information instead of manually.

To use this, download (or git clone) this repo into a folder, then:

- Firefox: go to `about:debugging` -> This Firefox -> Load Temporary Add-on... -> select the `manifest.json`

- Opera: go to `opera:extensions` -> Load unpacked -> select the folder that contains the manifest.json

This uses a postgres database and grpahql endpoint [hosted on heroku](http://jp-discord-music-bot-test.herokuapp.com/graphql).

Try using the graphql endpoint with the query:

```
query {
  songs {
    edges {
      node {
        songId
        name
        artists {
          edges {
            node {
              artistId
              name
            }
          }
        }
      }
    }
  }
}
```

To look at the code hosted on heroku, try doing `git clone https://git.heroku.com/jp-discord-music-bot-test.git`. You'll need to have git installed.
