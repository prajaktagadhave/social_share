Share Counts
============

I have always struggled with getting all the various share buttons from Facebook, Twitter, Google Plus, Pinterest, etc to align correctly and to not look like a tacky explosion of buttons.  Seeing a number of sites rolling their own share buttons with counts, for example [The Next Web](http://thenextweb.com/shareables/2012/05/08/move-over-zuck-abraham-lincoln-filed-a-patent-for-facebook-in-1845/) I decided to look into the various APIs on how to simply return the share count.

Twitter
-------

`http://cdn.api.twitter.com/1/urls/count.json?url=http://stylehatch.co`

Returns:
`{
   "id": "http://stylehatch.co",
   "shares": 61
}`