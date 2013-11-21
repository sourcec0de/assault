# assault

To get started run

```shell
npm install assault -g
```

here is an example of cli usage
```shell
assault -f ./request.json -m 1000 -c 10 -t 10000
```

The above command starts a queue with the contents of the request file
sets the max number of requests to `1000` and the concurrency to `10`.
It also sets a timeout of `10000` ms. No request can take more than 10000ms. 


The data in the request file can contain any valid Object that can be accepted
by the `request` npm module. This is an example of a `POST` with a raw JSON body.
This also sets `Content-Type: application/json` in the request headers.

contents of `./request.json`

```json
{
    "method":"POST",
    "url":"https://api.SOMEAPI.com/someEndPoint",
    "json":{
        "query":"JSON PARAM"
    },
    "timeout":10000
}
```

assault will respond with information about the load test

- `CODE:` Each Response Code
- `NUM:` Number of Requests that got that respons
- `MS:` Average response time

```
CODE: 200 NUM: 101 MS: 386.4752475247525
CODE: 500 NUM: 13 MS: 84.123135
```


### MORE CONCISE INSTRUCTIONS TO COME