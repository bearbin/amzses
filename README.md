go-ses
======

This is a Go package to send emails using Amazon's Simple Email Service.

Installation
------------

    go get github.com/bearbin/go-ses

Usage
-----

Then create and use an ses object:

    ses, err := ses.Init(username, secretkey, endpoint)
    response, err := ses.SendMail("info@example.com", "user@gmail.com", "Welcome!", "Welcome to our project!\n\n...")

The first return value is the response string from the server. To extract the message and request IDs:

    var resp ses.AmazonResponse
    err := xml.Unmarshal([]byte(response), &resp)
    // resp.MessageId, resp.RequestId

About
-----

The original library was written by Patrick Crosby at [StatHat](http://www.stathat.com).
