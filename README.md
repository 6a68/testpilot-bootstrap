# testpilot-wrapper

So [darkwing](https://github.com/dannycoates/darkwing) is a great idea, with just one problem: WebExtension API experiments aren't available until special Mozilla-only WebExtension APIs are possible (current target is 57).

But what if we wanted to get rid of the test pilot addon today?

We could provide experiments with a bootstrapped wrapper extension that provided all the functionality currently provided by the Test Pilot addon:
- metrics: could just fire a message to the embedding addon, instead of using a BroadcastChannel to fire the message across addons
- surveys: could again be implemented on a per-addon basis (though we'll need to be sure we don't annoy users by surveying from multiple addons at once)
- A/B testing: replace cross-addon messages with messages between the embedded webextension and the embedding bootstrapped addon

What about the test pilot addon with its button? This could also be an embedded webextension.
