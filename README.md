## README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

# Atum API

We built an API for the Atum data. The documentation for this API is accessible under following link:

[https://htmlpreview.github.io/Atum_API](https://htmlpreview.github.io/?https://github.com/psunix/atum/blob/master/doc/api_doc/index.html)

# Meteoblue API

## Expected sunshine time

### Resource URL

http://my.meteoblue.com/packages/clouds-1h

### Parameters

| Name          | Required      | Description  | Example |
| ------------- |:-------------:| ---------------------------------:|-------------------:|
| API Key       | True    | The Key from Metroblue get access |apikey=fdgdrt34tgrs |
| lat     | True     | degree of latitude| lat=47.5584|
| lon    | True     | degree of longitude | lon=7.57327 |
| asl | False | elevation | asl=342 |
| tz | False | timezone | tz=Europe%2FZurich|
| temperature | False |temperature format | temperature=C |
| timeformat | False | timeformat | timeformat=Y-M-D|


## Active Jobs

### Descripton

There is a ActiveJob in the lib/weather_provider/meteoblue.rb with the client to get the JSON.
With this we request the Sunshine Data for the various Locations.
We check once per two houres if Meteoblue updated their Data, if they did we send a request for each location we have and execute the ActiveJob.


### Save
The Data are Saved in the sunshinetime table. The job can check the ID = FK from the sunshinetable and override the start (DateTime) and the minutes_per_hour (string).







