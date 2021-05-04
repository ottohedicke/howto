# Quickstart / Start here

## How do I connect to the OTTO Market API?

Before you´re connecting your services to the OTTO Market you should test and develop your integration.
For this purpose OTTO established two test environments (sandbox & nonlive) so you can be sure you´re well prepared for the live environment.
Below you´ll find the URL´s of our environments.

### Sandbox-URL (testing)
```
https://sandbox.api.otto.market
```

### Nonlive-URL (testing)
```
https://nonlive.api.otto.market
```

After your integration was successfull, you will use the following URL to the OTTO Market.

### Live-URL
```
https://api.otto.market
```

Now that you know about the different URL´s you´ll learn how to get access.
Firstly you´ll need a `username` and a `password`. These are unique for each environment (live, nonlive, sandbox).

[Link]How to register as a **Partner**

If you´re a **service provider** interessted in adding a connection to the OTTO Market to your services please use this [Link]e-mail.
We´ll happily set you up with user credentials so you can start developing asap!

## Fetch Access Token for sandbox-environment

In order to fetch an authorization token you must have an API user with a password. You can use the following cURL command to receive your token.
Make sure you include your username and password in the command (without leading and trailing < >).

``` curl
curl -X POST \
  https://sandbox.api.otto.market/v1/token \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -H 'cache-control: no-cache' \
  -d 'username=<YourUsername>&password=<YourPassword>&grant_type=password&client_id=token-otto-api'
```

## Fetch Access Token for nonlive-environment

In order to fetch an authorization token you must have an API user with a password. You can use the following cURL command to receive your token.
Make sure you include your username and password in the command (without leading and trailing < >).

``` curl
curl -X POST \
  https://nonlive.api.otto.market/v1/token \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -H 'cache-control: no-cache' \
  -d 'username=<YourUsername>&password=<YourPassword>&grant_type=password&client_id=token-otto-api'
```

## Fetch Access Token for live-environment

In order to fetch an authorization token you must have an API user with a password. You can use the following cURL command to receive your token.
Make sure you include your username and password in the command (without leading and trailing < >).

``` curl
curl -X POST \
  https://api.otto.market/v1/token \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -H 'cache-control: no-cache' \
  -d 'username=<YourUsername>&password=<YourPassword>&grant_type=password&client_id=token-otto-api'
```

### Response-Example 

```JSON
{
  "access_token": "eyJhbGciOiJSUzI1NiISInR5cCIgOiAiSldUIiwia2lkIiA6ICJTd3ExRDRvYVBKUFQzMER3dmlZRkVVV2hRaEJtMEdPRlpWVWIwYWEteDBjIn0.eyJqdGkiOiIyMTg5Y2NjNC02NjU5LTQ1YmMtYjliMS1jYTIzMDMxOGQ3NmQiLCJleHAiOjE1ODQ5ODg3NjQsIm5iZiI6MCwiaWF0IjoxNTg0OTg1MTY0LCJpc3MiOiJodHRwczovL2VzYi13cy5vdHRvLmRlL3NlYy1hcGkvYXV0aC9yZWFsbXMvb3R0by1wYXJ0bmVyIiwic3ViIjoiODkwYmZkYjEtMTJkZS00OTY0LWJmMzgtYWQ1NzEyOTc4NjU4IiwidHlwIjoiQmVhcmVyIiwiYXpwIjoidG9rZW4tb3R0by1hcGkiLCJhdXRoX3RpbWUiOjAsInNlc3Npb25fc3RhdGUiOiIzZTA3MTBiMi1iNTdhLTRjYjAtYTUxZC02ZGU2MGE5OTczNTYiLCJhY3IiOiIxIiwic2NvcGUiOiJwdW1iYS1yb2xlcy1hcHAtcG9ydGFsIHBhcnRuZXIgZW1haWwgcHJvZmlsZSIsImVtYWlsX3ZlcmlmaWVkIjp0cnVlLCJyZWFsbV9hY2Nlc3MiOnsicm9sZXMiOlsiUHJvZHVjdHNfV3JpdGUiLCJSZWNlaXB0c19OYXZpZ2F0aW9uX1JlYWQiLCJTZXBhTWFuZGF0ZXNfQ3VzdG9tZXJTdXBwb3J0X1dyaXRlIiwiQnJhbmRzaG9wX05hdmlnYXRpb25fUmVhZCIsIkNhcnJpZXJBbmRSZXR1cm5fTmF2aWdhdGlvbl9SZWFkIiwiUGFydG5lcl9OYXZpZ2F0aW9uX1JlYWQiLCJTZXJ2aWNlc19OYXZpZ2F0aW9uX1JlYWQiLCJBbmFseXRpY3NfTmF2aWdhdGlvbl9SZWFkIiwiUHJvZHVjdHNfTmF2aWdhdGlvbl9SZWFkIl19LCJuYW1lIjoiVGVzdCBVc2VyIiwicHJlZmVycmVkX3VzZXJuYW1lIjoiYXBpX3Rlc3QiLCJsb2NhbGUiOiJkZSIsImdpdmVuX25hbWUiOiJUZXN0IiwiZmFtaWx5X25hbWUiOiJVc2VyIiwiZW1haWwiOiJhbmRyZS5lcmtAb3R0by5kZSJ9.Rszr6jXUUGGHzqw2XVo7HcaZ0pHvwYyJdg0olZEwpkz2lNBPejFPDuHK5eUrKEBxOhAsu3zKXwrfcyMWW8iufAbfCEonlDjle7U3NafLT-ITcjiL0wf1oI0D33h37RKmd0KjBXcoZRyvGZEUoItMp1WNGLn0JV8UvSOqDiGeCHvuurLNb91aIIHNMuN8lRQLaOhCKRmKsnxpUOytNcOER0_Z_sbK3x4fWJuaEDLIf6OGmx6TXZQr5e2UnvtOIWpt_JMvnKoJOC2-cPN5MP-PiMKTodi7ajhavUxo7dWyE0eBvc2stMFhjwSJO1KUkGjHdk0PWt-4GNlAdBze3laR2Q",
  "expires_in": 3600,
  "refresh_expires_in": 7200,
  "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICI5YjRjZjM1Yi0yZDBkLTQzZGUtYWVjMC1kZTUzMDNiYjM3YjEifQ.eyJqdGkiOiI2NDI0ZTg5OC0yMTBkLTRhZGYtYWNhOS1hZmI1YjA4NTU0NDMiLCJleHAiOjE1ODQ5OTIzNjQsIm5iZiI6MCwiaWF0IjoxNTg0OTg1MTY0LCJpc3MiOiJodHRwczovL2VzYi13cy5vdHRvLmRlL3NlYy1hcGkvYXV0aC9yZWFsbXMvb3R0by1wYXJ0bmVyIiwiYXVkIjoiaHR0cHM6Ly9lc2Itd3Mub3R0by5kZS9zZWMtYXBpL2F1dGgvcmVhbG1zL290dG8tcGFydG5lciIsInN1YiI6Ijg5MGJmZGIxLTEyZGUtNDk2NC1iZjM4LWFkNTcxMjk3ODY1OCIsInR5cCI6IlJlZnJlc2giLCJhenAiOiJ0b2tlbi1vdHRvLWFwaSIsImF1dGhfdGltZSI6MCwic2Vzc2lvbl9zdGF0ZSI6IjNlMDcxMGIyLWI1N2EtNGNiMC1hNTFkLTZkZTYwYTk5NzM1NiIsInNjb3BlIjoicHVtYmEtcm9sZXMtYXBwLXBvcnRhbCBwYXJ0bmVyIGVtYWlsIHByb2ZpbGUifQ.X02NuyvlIhGL6L6fDGvdW-NSLCpFFIc4Cf8XbA_bBdk",
  "token_type": "bearer",
  "not-before-policy": 0,
  "session_state": "3e0710b2-b57a-4cb0-a51d-6de60a997356",
  "scope": "pumba-roles-app-portal partner email profile"
}
```

Extract the value from `"access_token"` and use it as the bearer token for authentication.

## Refresh Token

The refresh token can be extracted from the `"refresh_token"` value. Once the access token is expired you can use the refresh token to get a new access token, without using your users credentials again. You can use the following cURL command. Include the refresh token (without leading and trailing < >).

```
curl -X POST \
  https://api.otto.market/v1/token \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -H 'cache-control: no-cache' \
  -d 'refresh_token=<refresh_token>&grant_type=refresh_token&client_id=token-otto-api'
```

