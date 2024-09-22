```
import dialogflow
from dialogflow.types import Intent, IntentMessage
import os

os.environ['GOOGLE_APPLICATION_CREDENTIALS'] = 'prashant2.0-credentials.json'
dialogflow_client = dialogflow.SessionsClient()

INTENTS = [
    Intent(display_name='Greeting', intent_id='greeting'),
    Intent(display_name='Knowledge Sharing', intent_id='knowledge-sharing'),
    Intent(display_name='Innovation', intent_id='innovation'),
    Intent(display_name='Fun', intent_id='fun')
]

ENTITIES = [
    'Name',
    'Interest',
    'Location'
]

API_ENDPOINT = '/prashant2.0/api'
MOBILE_APP_FRAMEWORK = 'Flutter'

class Prashant2Model:
    def __init__(self):
        self.intents = INTENTS
        self.entities = ENTITIES

    def process_intent(self, intent):
        if intent.display_name == 'Greeting':
            return 'Hello! How can I assist you today?'
        elif intent.display_name == 'Knowledge Sharing':
            return 'What would you like to know?'
        elif intent.display_name == 'Innovation':
            return 'What innovative idea do you have?'
        elif intent.display_name == 'Fun':
            return 'Let\'s have some fun!'

prashant2_model = Prashant2Model()

def handle_api_request(request):
    intent = request.json['intent']
    response = prashant2_model.process_intent(intent)
    return {'response': response}

def handle_mobile_app_request(request):
    intent = request.json['intent']
    response = prashant2_model.process_intent(intent)
    return {'response': response}

if __name__ == '__main__':
    from flask import Flask, request, jsonify
    app = Flask(__name__)

    @app.route(API_ENDPOINT, methods=['POST'])
    def handle_api_request_endpoint():
        return jsonify(handle_api_request(request))

    @app.route('/mobile-app', methods=['POST'])
    def handle_mobile_app_request_endpoint():
        return jsonify(handle_mobile_app_request(request))

    app.run(debug=True)
```


```
{
  "agent": {
    "id": "prashant2.0",
    "name": "Prashant2.0",
    "language": "en",
    "timeZone": "IST"
  },
  "intents": [
    {
      "id": "greeting",
      "name": "Greeting",
      "trainingPhrases": [
        "Hello",
        "Hi"
      ],
      "response": "Hello! How can I assist you today?"
    },
    {
      "id": "knowledge-sharing",
      "name": "Knowledge Sharing",
      "trainingPhrases": [
        "What is AI?",
        "How does machine learning work?"
      ],
      "response": "What would you like to know?"
    },
    {
      "id": "innovation",
      "name": "Innovation",
      "trainingPhrases": [
        "I have an innovative idea",
        "How can I improve AI?"
      ],
      "response": "What innovative idea do you have?"
    },
    {
      "id": "fun",
      "name": "Fun",
      "trainingPhrases": [
        "Let's have fun",
        "Tell me a joke"
      ],
      "response": "Let's have some fun!"
    }
  ],
  "entities": [
    {
      "id": "name",
      "name": "Name",
      "type": "string"
    },
    {
      "id": "interest",
      "name": "Interest",
      "type": "string"
    },
    {
      "id": "location",
      "name": "Location",
      "type": "string"
    }
  ]
}
```


```
dialogflow
flask
json
``````
import dialogflow
from dialogflow.types import Intent, IntentMessage
import os

os.environ['GOOGLE_APPLICATION_CREDENTIALS'] = 'prashant2.0-credentials.json'
dialogflow_client = dialogflow.SessionsClient()

INTENTS = [
    Intent(display_name='Greeting', intent_id='greeting'),
    Intent(display_name='Knowledge Sharing', intent_id='knowledge-sharing'),
    Intent(display_name='Innovation', intent_id='innovation'),
    Intent(display_name='Fun', intent_id='fun')
]

ENTITIES = [
    'Name',
    'Interest',
    'Location'
]

API_ENDPOINT = '/prashant2.0/api'
MOBILE_APP_FRAMEWORK = 'Flutter'

class Prashant2Model:
    def __init__(self):
        self.intents = INTENTS
        self.entities = ENTITIES

    def process_intent(self, intent):
        if intent.display_name == 'Greeting':
            return 'Hello! How can I assist you today?'
        elif intent.display_name == 'Knowledge Sharing':
            return 'What would you like to know?'
        elif intent.display_name == 'Innovation':
            return 'What innovative idea do you have?'
        elif intent.display_name == 'Fun':
            return 'Let\'s have some fun!'

prashant2_model = Prashant2Model()

def handle_api_request(request):
    intent = request.json['intent']
    response = prashant2_model.process_intent(intent)
    return {'response': response}

def handle_mobile_app_request(request):
    intent = request.json['intent']
    response = prashant2_model.process_intent(intent)
    return {'response': response}

if __name__ == '__main__':
    from flask import Flask, request, jsonify
    app = Flask(__name__)

    @app.route(API_ENDPOINT, methods=['POST'])
    def handle_api_request_endpoint():
        return jsonify(handle_api_request(request))

    @app.route('/mobile-app', methods=['POST'])
    def handle_mobile_app_request_endpoint():
        return jsonify(handle_mobile_app_request(request))

    app.run(debug=True)
```


```
{
  "agent": {
    "id": "prashant2.0",
    "name": "Prashant2.0",
    "language": "en",
    "timeZone": "IST"
  },
  "intents": [
    {
      "id": "greeting",
      "name": "Greeting",
      "trainingPhrases": [
        "Hello",
        "Hi"
      ],
      "response": "Hello! How can I assist you today?"
    },
    {
      "id": "knowledge-sharing",
      "name": "Knowledge Sharing",
      "trainingPhrases": [
        "What is AI?",
        "How does machine learning work?"
      ],
      "response": "What would you like to know?"
    },
    {
      "id": "innovation",
      "name": "Innovation",
      "trainingPhrases": [
        "I have an innovative idea",
        "How can I improve AI?"
      ],
      "response": "What innovative idea do you have?"
    },
    {
      "id": "fun",
      "name": "Fun",
      "trainingPhrases": [
        "Let's have fun",
        "Tell me a joke"
      ],
      "response": "Let's have some fun!"
    }
  ],
  "entities": [
    {
      "id": "name",
      "name": "Name",
      "type": "string"
    },
    {
      "id": "interest",
      "name": "Interest",
      "type": "string"
    },
    {
      "id": "location",
      "name": "Location",
      "type": "string"
    }
  ]
}
```


```
dialogflow
flask
json
```
