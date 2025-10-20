# sts-cloudonix

sts-cloudonix is a server which enables calls made to Cloudonix Voice Applications to pass through to Deepgram's [Voice Agent API](https://developers.deepgram.com/docs/voice-agent), enabling the caller to talk to a voice agent/bot.

See the following [Guide in our Documentation](https://developers.deepgram.com/docs/twilio-and-deepgram-voice-agent) for more information.

## What is Deepgram?

[Deepgram's](https://deepgram.com/) voice AI platform provides APIs for speech-to-text, text-to-speech, and full speech-to-speech voice agents. Over 200,000+ developers use Deepgram to build voice AI products and features.

## Pre-requisites

You will need:
* A [Cloudonix account](https://cloudonix.com/signup) with an active Twilio number (the free tier will work).
* A Deepgram API Key - [get an API Key here](https://console.deepgram.com/signup?jump=keys).
* (_Optional_) [ngrok](https://ngrok.com/) to let Cloudonix access a local server.
* A valid `Cloudonix Container Application` Configuration in your [Cloudonix Account](https://developers.cloudonix.com/Documentation/accountManagement/hostedApplicationsManagement) like the following:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Response>
    <Say language="en">"This call may be monitored or recorded."</Say>
    <Connect>
        <Stream url="wss://a127-75-172-116-97.ngrok-free.app/cloudonix" />
    </Connect>
</Response>
```
You should replace the url with wherever you decide to deploy sts-cloudonix. In the [Guide in our Documentation](https://developers.deepgram.com/docs/twilio-and-deepgram-voice-agent) we use ngrok to expose the server running locally and this is the recommended way for quick development.

This `Cloudonix Container Application` must also be [attached to a Cloudonix voice application](https://developers.cloudonix.com/Documentation/accountManagement/voiceApplicationsManagement) and [assigned with a DID](https://developers.cloudonix.com/Documentation/accountManagement/voiceApplicationsManagement#step-2-assign-a-dnid-to-your-voice-application) so that it gets executed whenever someone calls that number.

## Running the Server

Install requirements:

```bash
pip install -r requirements.txt
```

## Set your Deepgram API Key

In your terminal run:

```bash
export DEEPGRAM_API_KEY "Your key here"
```

If your `Cloudonix Container Application` is setup correctly, you should be able to just run the server with:

```bash
python server.py
```
and then start making calls to the phone number the Voice Application is attached to!

## Code Tour

For a guided tour of the code, see the following [Guide in our Documentation](https://developers.deepgram.com/docs/twilio-and-deepgram-voice-agent).


## Getting Help

- Found a bug? [Create an issue](https://github.com/greenfieldtech-nirs/sts-cloudonix/issues)
- [Join the Deepgram Github Discussions Community](https://github.com/orgs/deepgram/discussions)
- [Join the Deepgram Discord Community](https://discord.gg/xWRaCDBtW4)

## Author
Authored by: [Nir Simionovich](https://github.com/greenfieldtech-nirs)
Forked from: [Deepgram](https://deepgram.com)
