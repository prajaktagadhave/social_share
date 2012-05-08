Share Counts
============

I have always struggled with getting all the various share buttons from Facebook, Twitter, Google Plus, Pinterest, etc to align correctly and to not look like a tacky explosion of buttons.  Seeing a number of sites rolling their own share buttons with counts, for example [The Next Web](http://thenextweb.com/shareables/2012/05/08/move-over-zuck-abraham-lincoln-filed-a-patent-for-facebook-in-1845/) I decided to look into the various APIs on how to simply return the share count.

Twitter
-------

**GET URL:**

`http://cdn.api.twitter.com/1/urls/count.json?url=http://stylehatch.co`

**Returns:**
```json
{
	"count":528,
	"url":"http://stylehatch.co/"
}
```

Facebook
--------

**GET URL:**

`http://graph.facebook.com/?id=http://stylehatch.co`

**Returns:**

```json
{
   "id": "http://stylehatch.co",
   "shares": 61
}
```

LinkedIn
--------

**GET URL:**

`http://www.linkedin.com/countserv/count/share?url=http://stylehatch.co&format=json`

**Returns:**

```json
{
	"count":17,
	"fCnt":"17",
	"fCntPlusOne":"18",
	"url":"http:\/\/stylehatch.co"
}
```

Google Plus
-----------

**POST URL:**

`https://clients6.google.com/rpc?key=YOUR_API_KEY`

**POST body:**

```json
[{
	"method":"pos.plusones.get",
	"id":"p",
	"params":{
		"nolog":true,
		"id":"%%URL%%",
		"source":"widget",
		"userId":"@viewer",
		"groupId":"@self"
		},
	"jsonrpc":"2.0",
	"key":"p",
	"apiVersion":"v1"
}]
```

**Returns**
```json

[{
	"result": { 
		"kind": "pos#plusones", 
		"id": "http://www.google.com/", 
		"isSetByViewer": false, 
		"metadata": {
			"type": "URL", 
			"globalCounts": {
				"count": 3097.0
			}
		}
	} ,
	"id": "p"
}]
```