# Overview

You'll build a basic URL shortener!

# Time
It's important to us that you spend at least one hour on this exercise, and NO MORE than three hours. Please [set a timer](https://www.google.com/search?q=timer+3+hours) for 3 hours and don't invest any additional time! This exercise is meant to be fodder for meaningful discussion with a real human, not a pass/fail or automate-able project submission.


# Features
Given our commitment to your time, please consider tackling these features in the order we've listed. That way, if you want to end a bit early, you'll have already addressed the pieces we think are the most interesting to discuss.

# Step 1: the URL model and redirect endpoint
Build a table/model to store URLs. Use whatever database system you prefer (we used rails + sqlite), but please do use some sort of DBMS persistence (no raw files on disk or in memory, please!)

Hardcode some data into your database and use this model to power your first HTTP endpoint! You can use any URL scheme/convention; we went with `/urls/:id`, where `:id` is the shortened URL key

Visiting this endpoint should perform the URL lookup and, if a matching URL is found, redirect the user to the un-shortened target URL


## Example
Given a shortened URL where `abc` unfolds to `https://google.com?q=def`, a visit to `http://localhost/urls/abc` should result in a redirect to `https://google.com?q=def`

```bash
curl -I localhost:3000/urls/abc
# HTTP/1.1 302 Found
# <...maybe some more headers here>
# Location: https://google.com?q=def # this is the important one
# Content-Type: text/html; charset=utf-8
# Cache-Control: no-cache
```

## Considerations
 - do we need any uniqueness constraints?

# Step 2: UI & endpoints for listing and creating URLs

Again, the URL structure is up to you, but we went with:
- `GET /urls` to render the list of shortened URLs currently in the database
- `GET /urls/new` to render the new URL page & form, and
- `POST /urls` to create new URLs

## URLs list page
This doesn't need to be fancy! Here's ours:

![image](https://user-images.githubusercontent.com/3535390/170588078-139e5977-6d5a-4e62-934b-2203ad61ba8c.png)


We'll want to see two main pieces of info for each shortened URL in the database:
- the short key
- the unshortened URL

Also, it'd be great to add a link from this page to the "new URL page" for convenience


## New URL Page
This page will need
- A text input so a user can input the short key for a new shortened URL
- Similar text input for the unshortened target URL
- A button to submit the form and create the URL

Again, here's our super sketchy example:

![image](https://user-images.githubusercontent.com/3535390/170588217-140598e1-f50b-452d-ad3f-e120d3878805.png)



## Create URL endpoint
This endpoint will accept the form submission from the new URL page and insert the new URL record into the database.

It's up to you how you incorporate this endpoint with the rest of the flow, but make sure the user can list & create URLs seamlessly, without having to manually update the browser's address bar.

# Step 3: You're done! (if you want)
If you haven't yet reached your 1-hour minimum, or you have some time left before your 3 hours is up, here are some things we'd think would make this app even better:
- some UX polish (we didn't make it this far, as you can see from the screenshots)
- a unit test or two (these are our favorite)
- some validations: what should our app do if a key is taken, or if a field is left blank?
- a new feature: track the number of times each shortened URL has been unfolded & visited, and show count on the URL list page
- auto-generate keys instead of taking user input

# Submission
- Add some instructions to help us get your code's programming language & dependencies installed
- Create a zip file of your repo (if you're using git, `git archive --format=zip --output project.zip` will do it for ya) and make it available to `leith@meritamerica.org` via your file-sharing service of choice (or just send it straight through email if it's not too big)

Thanks so much for your time and interest at working for Merit America! We'll be in touch soon.
