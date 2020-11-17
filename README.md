# music-thingy-browser-extension

Warning: this is under active development and most probably will break very frequently.

This is the browser extension for my music database thingy.

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
