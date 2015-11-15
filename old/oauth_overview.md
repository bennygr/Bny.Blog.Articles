<!--
Title:"OAuth 1.0 authentication overview",
Date:"2014-05-22T22:35+0200",
Tags:"OAuth, Security",
PreviewLength:"216",
-->

OAuth is an authentication protocol which allows the authentication of a client to a server without knowing the user's name and password. This article gives a short overview about the OAuth 1.0 authentication flow.

### OAuth authentication flow - An example in simple terms

The following example is based on Rob Sober's German article ["Einführung in OAuth"](http://sites.varonis.com/de/2012/06/13/einfuhrung-in-oauth-ohne-fachchinesisch/) and describes the OAuth authentication of a user's beautiful desktop Twitter-client called "[Birdie](http://birdieapp.github.io/)".

_Step 1:_ The user triggers the authentication process by using the consumer:

`John: "Birdie, I want you to post this tweet in my twitter-stream!"`
`Birdie: "John, thats cool! I'm going to request a "request token" from twitter."`

_Step 2:_ The consumer requests a "request token" from the service:

`Birdie: "Hello Twitter, a user wants me to post tweets in his stream, could you please send me a request token?" `
`Twitter: "Sure, here is a request token and a secret."`

_Step 3:_ The user is redirected to the service

`Birdie: "OK, John, I'm going to redirect you to twitter in order to confirm my request. Here is my request token"`
`John: "OK!"`

_Step 4:_ The user confirms the consumer's request token

`John: "Hello Twitter I want to confirm..."`
`Twitter: "STOP, WHO ARE YOU?"`
`John: "Oh sorry, my name is John and my password is "123"" (Note: At this point John should be really ensure that he is talking to Twitter, and not to an evil phishing site)`
`Twitter: "OK, hello John."`
`John: "I want to confirm this request token from Birdie."`
`Twitter: "Are you sure you want to allow Birdie to post in your stream?"`
`John: "Yes."`
`Twitter: "OK, I'm going to redirect you back to Birdie. Please tell him that his request token has been authorized."`

_Step 5:_ The consumer requests an "access token"

`Birdie: "Twitter, I want change my "request token" into an "access token". Here is my request token and my secret."`
`Twitter: "OK, here is your "access token" and the secret"`

_Step 6:_ The consumer uses the "access token" for authentication 

`Birdie:"Twitter, I want to post this nice little tweet into John's stream. Here is my "access token".`"
`Twitter: "Done! A really nice tweet!"`

### The detailed OAuth authentication flow in a single picture

The following illustration, created by the guys of the [DevDefined.OAuth](https://code.google.com/p/devdefined-tools/wiki/OAuth) project (which is an OAuth library for .NET), shows the detailed authentication flow of OAuth pretty well.

![oauth](https://raw.githubusercontent.com/bittercoder/DevDefined.OAuth/master/artifacts/Oauth_diagram.png)
