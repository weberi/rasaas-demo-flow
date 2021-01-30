
# rasaas demo flow

This Node-Red flow implements an action server for a Rasa chatbot. It can execute customaction for the weatherbot in  https://github.com/JustinaPetr/Weatherbot_Tutorial.
It requires a Node-Red installation including  ``node-red-contrib-rasa-actionserver``.
## Included flows
### webhook
The main flow starts at /webhook; branches into two actions.
- Action_weather calls weatherstack api
- Action_more calls wikipedia api

The flow demos the use of the rasaas nodes. ``setslots`` node is not needed at all, but included into the flow for demoing its usage

### health
sends back status ok

### actions
sends back a list of the actions it supports. The actions have to be entered manually.

### Catchall
catches errors and reports the error message to Rasa. Returns status code 500.