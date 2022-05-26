# Overview

You'll build a basic URL shortener!

# Time
It's important to us that you spend at least one hour on this exercise, and NO MORE than three hours. Please [set a timer](https://www.google.com/search?q=timer+3+hours) for 3 hours and don't invest any additional time! This exercise is meant to be fodder for meaningful discussion with a real human, not a pass/fail or automate-able project submission.


# Features
Given our commitment to your time, please consider taking these features in the order we've listed. That way, if you want to end a bit early, you'll have already addressed the pieces we think are the most intresting to discuss.

# Step 1: the URL model and redirect endpoint
Build a table/model to store URLs. Use whatever database system you prefer, but please do use some sort of DBMS persistance (no raw files on disk or in memory, please!)

Use this model to power your first HTTP endpoint! You can use any URL scheme/convention; we went with `/urls/:id`, where `:id` is the shortened URL key

Visiting this endpoint should perform the URL lookup and, if a matching URL is found, redirect the user to the un-shortened target URL


## Example
Given a shortened URL where `abc` unfolds to `https://google.com?q=def`, a visit to `http://localhost/urls/abc` should result in a redirect to `https://google.com?q=def`

```
17:39 $ curl -I localhost:3000/urls/abc
HTTP/1.1 302 Found
<...maybe some more headers here>
Location: https://google.com?q=def # this is the important one
Content-Type: text/html; charset=utf-8
Cache-Control: no-cache
```

# Step 2: UI & endpoints for listing and creating URLs

Again, the URL structure is up to you, but we went with:
- `GET /urls` to render the list of shortened URLs currently in the database
- `GET /urls/new` to render the new URL page & form, and
- `POST /urls` to create new URLs

## URLs list page
This doesn't need to be fancy!


We'll want to see two main pieces of info for each shortened URL in the database:
- the short key
- the unshortened URL

Also, it'd be great to add a link from this page to the "new URL page" for convenience


## New URL Page
This page will need
- A text input so a user can input the short key for a new shortened URL
- Similar text input for the unshortened target URL
- A button to submit the form and create the URL


## Create URL endpoint
This endpoint will accept the form submission from the new URL page and insert the new URL record into the database.
