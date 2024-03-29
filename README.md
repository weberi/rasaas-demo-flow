
# RasaasDemo

This Node-Red flow implements an action server for a Rasa chatbot. 
It requires a Node-Red installation including  ``node-red-contrib-rasa-actionserver`` (``rasaas``).
It can execute custom actions for a slightly extended version of the weatherbot of  https://github.com/JustinaPetr/Weatherbot_Tutorial.
You can ask the bot for weather informaton for a specific location, and you can ask  for more info about a  location.
The weather bot will call the action server which will access weatherstack api or wikipedia api, depending on the user intent. 
You need to provide a valid access key for weatherstack api in the flow.
![RasaasDemoFlow](RasaasDemoFlow.png)
## Endpoints
### webhook
The main flow starts at /webhook; it branches into three actions.
- Action_weather calls weatherstack api
- Action_generalinfo calls wikipedia api
- Action_clearlocation empties a slot ``location``.

The flow demos the use of the rasaas nodes. 

### health
sends back status ok

### actions
sends back the list of supported actions. The actions have to be entered manually in the node.

### Catchall
catches errors and reports the error message to Rasa. Returns HTTP status code 500.

## Try it out
### Chatbot data
Data and config files for a very preliminary version of the weather chatbot are provided, which you may use for training the chatbot. (Rasa Version: 2.2.x)

### Test it manually with Postman 
Two sample requests are provided for manual testing of the action server with Postman. (I.e., no need to install the Rasa Bot for issuing requests to the ActionServer)

## References
- https://github.com/JustinaPetr/Weatherbot_Tutorial
- https://rasa.com/docs/rasa/
  - Weber, Irene: [Low-code from frontend to backend: Connecting conversational user interfaces to backend services via a low-code IoT platform](https://dl.acm.org/doi/10.1145/3469595.3469632). In: CUI 2021 - 3rd Conference on Conversational User Interfaces. Bilbao (online) Spain : ACM, 2021 — DOI 10.1145/3469595.3469632. ([preprint](https://opus4.kobv.de/opus4-hs-kempten/frontdoor/index/index/docId/978))
