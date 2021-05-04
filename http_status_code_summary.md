# HTTP Status Code Summary

There may be times you´ll run into problems.
Luckily HTTP Status Codes and Error Messages give a hint on how to solve the problem.

You´ll find the common HTTP error states in the table below:

|State|Message|
|---|---|
|**200** OK| Everything worked as expected.|
|**400** Bad Request|The request was unacceptable, often due to missing a required parameter.|
|**401** Unauthorized|No valid API key provided.|
|**402** Request Failed|The parameters were valid but the request failed.|
|**403** Forbidden|The API key doesn't have permissions to perform the request.|
|**404** Not Found|The requested resource doesn't exist.|
|**409** Conflict|The request conflicts with another request (perhaps due to using the same idempotent key).|
|**429** Too Many Requests|Too many requests hit the API too quickly.|
|**500, 502, 503, 504** Server Errors|Something went wrong on our end. (These are rare.)|

