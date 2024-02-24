Documentation:

<https://developers.facebook.com/docs/facebook-login/manually-build-a-login-flow/>

Prerequisites:

Facebook Account

curl

---

Client Registration:

<https://developers.facebook.com/>

create an app and add the Facebook Login product, set valid OAuth redirect URIs in the settings of the product,

needs to be an exact match, watch out for trailing slashes etc. (e.g.: <https://api-university.com/> != <https://api-university.com>)

your redirect URI needs to have a slash in the end, otherwise Facebook adds one!

What you need:

appId = clientId = 376825738396339

appSecret = clientSecret = 

redirectURI = <https://pizza-menu-ftju.vercel.app/>

URLENCODE(redirectURI) = https%3A%2F%2Fpizza-menu-ftju.vercel.app%2F

---

Authorization Endpoint (Browser):

<https://www.facebook.com/v6.0/dialog/oauth?client_id=376825738396339&redirect_uri=https%3A%2F%2Fpizza-menu-ftju.vercel.app%2F&state=987654321>

What you need to extract from the response:

code = AQCSixpQ0-GDkjWx0TsUIQY_0CRvhr-eCeLysjOjuTXPPwLFmWdRHK2TfnjaQkXKBH1_qW2J2DZ9sIeMpQDnULx0zU2zQm1lM3WMFVFrF1Vb2U8wI6bAn7ro7PRxfFDOO-GHPblyfRyk0cZ-0XTQtR8o8-L9-_o9G24BTkVRdHuKXv3d4AbLo9QWnT2S8DtSSQzyCgp6LYMDtp6K-z-kF5F6t7wD11kQ6D9nDk8v4P4aVdBVq0ozGaHgn8JcMaeN87x9jLk1sXcxgmLLnR0t7chjksUzcZO4LBxITMJHXxukRVgf17XJeAbNJDndnKJpKehInOb43M9yxmqw2xO4sGU3-KhUNGnFjm-SqrnHxvSvHDOiOh31VawKPu8Qy4Itfa8

---

Token Endpoint:

non-standard: it is a GET instead of a POST

```bash
curl -ik "https://graph.facebook.com/v6.0/oauth/access_token?redirect_uri=https%3A%2F%2Fpizza-menu-ftju.vercel.app%2F&client_id=376825738396339&client_secret=072a38272e62413a6c21d5e03f6c3018&code=AQBLTWM6PJPW5H2mz8y1S1Z2nU3Px7WdOgFvZXOSpcjixcIl4b6Ulp460d7zIR_JyjXxuJHOioOyYa45e7Nm4umRX4jECPbNGkPhxZPqDZD44N7eF0ag-zvueBVWr6hlFUdBHJgZ8quvQgG32ZOf78MchdRtmz7NRZmuM3gtGw3ZuFy5OiDmTG3kSWHSQSXDrLQtIRodZX8r-Gs-WQyJDHyTO-SRhdE-MU82f1BxaYxHTKbnJ7qFGkjaxyx8hzETBVrE5DI8nhJV8Ip-QsGMaLl0Cd5_SxVeO8M4AbrLaNzRdM7ZUS37PYQj6YORKn6kaZa_8zZzAzMsqhCio9zYgSjM7pF3jsQR1H16_aYDAi1h_vxATDo4jUPoUyowXUVpo54"
```

What you need from the response:

access_token = "EAAFWuJRHgrMBO0RSwCVVDYWBLTv2oWZB9mU5M4xWKdue7TCmIxKkco4yyGcxSzDX7vN71ZBp7SBns7eEv00CjlZAYEFnQCFj7tx7Efk8Dvw8SWwgDQ4yDg2WIhGD4jZCI20UsunCO6l0CnZAIEOuKOdEsHCm4vwGksroKW1VwZCYV7YgYPZBZBFehPtvrpZA95bak9SVNhyboZBNJcXvLrWkAKknRcffzZC4dX4GEl33DHqBdO0fCZC4rZAWZA"

---

Resource Access:

```bash
curl -H "Accept: application/json" -H "Authorization: Bearer EAAFWuJRHgrMBO0RSwCVVDYWBLTv2oWZB9mU5M4xWKdue7TCmIxKkco4yyGcxSzDX7vN71ZBp7SBns7eEv00CjlZAYEFnQCFj7tx7Efk8Dvw8SWwgDQ4yDg2WIhGD4jZCI20UsunCO6l0CnZAIEOuKOdEsHCm4vwGksroKW1VwZCYV7YgYPZBZBFehPtvrpZA95bak9SVNhyboZBNJcXvLrWkAKknRcffzZC4dX4GEl33DHqBdO0fCZC4rZAWZA" "https://graph.facebook.com/me"
```

What you need from the response:
{"name":"Chamara Chathuranga Weerasinghe","id":"4017994968431029"}
name =
