layout: default

Training a chat model using BuddhiNLP is very easy and straight forward. We use JSON file format to input data for training the model. The JSON file structure is as follows;

```json
{
    "intents": [{
            "tag": "greeting",
            "patterns": ["Hi", "How are you", "Is anyone there?", "Hello", "Good day"],
            "responses": ["Hello, How are you?", "Good to see you", "Hi there, how can I help?"]
        },
        {
            "tag": "goodbye",
            "patterns": ["Bye", "See you later", "Goodbye"],
            "responses": ["See you later!", "Have a nice day", "Bye!"]
        },
        {
            "tag": "thanks",
            "patterns": ["Thanks", "Thank you", "That's helpful"],
            "responses": ["Your welcome!", "Any time!", "My pleasure"]
        },
        {
            "tag": "fallback",
            "patterns": [""],
            "responses": ["Sorry, please say that again", "Please give me more info", "I still can't understand that."]
        }
    ]
}
```


This is the format of JSON file that we use as the training data for the chatbot.

**tag:** _(string)_ This is the intent name. Use lowercase alpha-numeric characters and underscore. Do not use any other symbols or capital letters.

**patterns:** (_Array<string>_) This is where we defined user utterances. Patterns of speech for the intent. This is a string array. You can define many patterns as you like. More the patterns are better the accuracy is.

**responses:** (Array<string>) Here we define the responses for the intent. This is also a string array. You can define variety of responses. Try to define variety of responses, so the chatbot won’t keep repeating the same response.

Now to train the model use the following code:

```javascript
buddhi.train('path/to/file.json', output_dir);
```

### Parameters

**datafile:** Path to training data file.

**output_dir:** Path to out put folder where the model will be saved. Use _[__dirname](https://nodejs.org/api/modules.html#modules_dirname)_ to save the model to the current directory of your project. Model files will be saved to this directory.
