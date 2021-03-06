---
date: 2016-03-08T21:07:13+01:00
title: HTTP
menu:
  main:
    parent: 'Sending Data'
    weight: 25
---

To send us a log all we required is:

* Valid JSON content
* ApiKey sent in the headers for ease
* Content type set to application/json
* You can POST or PUT your data
If you want to try it out copy this below and send it in!

```sh
curl -i -H "ApiKey: YOUR-API-KEY" -i -H "Content-Type: application/json" http://api.logit.io/v2 -d '{"test":"test","example": { "a": 1, "b": 2 } }'
```

Remember if you structure your data correctly you will have much easier life!

Optionally you can define the type of your data, this is important if you want to reuse the same fields but with different underlying types. Dont /worry if you dont set it we will set it to 'general' `LogType` is all you need to set in the headers e.g. `-H "LogType: example"`

You should get a response code of `202` from us otherwise you will get a `500`

```sh
HTTP/1.1 202 ACCEPTED
Server: nginx/1.6.0
Date: Mon, 02 May 2016 19:15:29 GMT
Content-Type: application/json
Content-Length: 25
{
  "message": "Thanks"
}
```
