FORMAT: 1A
HOST: http://polls.apiblueprint.org/

# Predictive Emotion Service

Artificial Intelligence (AI) is already part of our lives. Whenever you pick up your smartphone, you’re already seeing what AI can do for you, from tailored recommendations to relevant search results. With the Salesforce Predictive Emotion Service, you can build AI into your Salesforce org or apps without needing a Stanford PhD.

The Predictive Emotion Service is part of the Einstein suite of technologies, and you can use it to AI-enable your apps.
The Predictive Emotion Service takes data from heartbeats of a person, learns about how those correlate with that person's emotive state, and predicts whether the person is happy, sad, angry, or excited to an 87% accuracy.

You can use the service to ascertain mood data from heartbeat data. It analyzes small variations in heartbeat intervals to determine levels of emotion.

## Questions Collection [/questions]

### List All Questions [GET]

+ Response 200 (application/json)

        [
            {
                "question": "Favourite programming language?",
                "published_at": "2015-08-05T08:40:51.620Z",
                "choices": [
                    {
                        "choice": "Swift",
                        "votes": 2048
                    }, {
                        "choice": "Python",
                        "votes": 1024
                    }, {
                        "choice": "Objective-C",
                        "votes": 512
                    }, {
                        "choice": "Ruby",
                        "votes": 256
                    }
                ]
            }
        ]

### Create a New Question [POST]

You may create your own question using this action. It takes a JSON
object containing a question and a collection of answers in the
form of choices.

+ Request (application/json)

        {
            "question": "Favourite programming language?",
            "choices": [
                "Swift",
                "Python",
                "Objective-C",
                "Ruby"
            ]
        }

+ Response 201 (application/json)

    + Headers

            Location: /questions/2

    + Body

            {
                "question": "Favourite programming language?",
                "published_at": "2015-08-05T08:40:51.620Z",
                "choices": [
                    {
                        "choice": "Swift",
                        "votes": 0
                    }, {
                        "choice": "Python",
                        "votes": 0
                    }, {
                        "choice": "Objective-C",
                        "votes": 0
                    }, {
                        "choice": "Ruby",
                        "votes": 0
                    }
                ]
            }
