# create-hue-application-keys

Create the values required for the "hue-application-key" header in Hue Bridge API requests

## About

Invoke the Philips Hue Bridge API entry point to generate a client
application key required as a security token by most of the other API
entry points.

- The environment variable named `ADDRESS` must be set to the bridge's
  host name or IP address for each instance of this subflow.

- This subflow must be invoked within 30 seconds of pressing the large
  button on top of the bridge.

If successful, the generated client application key will be shown as
the `username` property inside a JSON object in the debug pane.

```
[
    {
        "success": {
            "username": <hue application key>,
            "clientkey": <ignore this>
        }
    }
]
```

The `username` string must be used as the value of the
`hue-application-key` header in subsequent HTTP requests sent to the
API on the given Hue bridge. You will need to perform this on each
Hue bridge.

See <https://developers.meethue.com/develop/hue-api-v2/getting-started/>
for details.