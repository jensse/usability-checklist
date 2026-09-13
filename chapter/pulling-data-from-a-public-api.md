# Pulling data from a public API


- [ ] You know what you are allowed to pull before you start pulling.
  - [ ] There is no stated request limit, that does not mean unlimited.
  - [ ] You asked the provider for the permitted rate if you plan to poll at high frequency, or to sell or resell the data.
- [ ] You pull as little as possible.
  - [ ] Initial full import: once.
  - [ ] Regular metadata refresh: every 15–60 minutes.
  - [ ] Routine background synchronization: every few hours, if minute-level changes are not important.
- [ ] You use the real-time service where one exists, instead of repeatedly polling.
  - [ ] Real-time availability comes through a stream (e.g. a WebSocket), so you receive changes rather than continually requesting the full dataset.
  - [ ] You obtain a connection URL using an API key, and connect using WebSockets.
- [ ] You verified the licence and terms of use for the dataset.
  - [ ] You know whether it is public domain, what the attribution clause is, and whether commercial use is permitted.
- [ ] You store the last response and only refresh when necessary.
  - [ ] The full dataset is downloaded once; subsequent requests only ask for changes.
- [ ] You have a plan for history.
  - [ ] The API does not provide historical data → you store successive real-time updates yourself, in your own storage.
- [ ] You keep an eye on the volume you actually generate.
  - [ ] Caching is on; the complete database is not repeatedly downloaded.
  - [ ] There is no polling loop that runs unattended without a bound.
