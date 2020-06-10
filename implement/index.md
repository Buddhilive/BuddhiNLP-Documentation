# Use Trained Model
Once you have [trained your model](https://github.buddhilive.com/train/) you can implement it using following code;

### Initialize Model

```javascript
const dataUrl = 'path/to/model_metadata.json';
const modelUrl = 'https://yourdomain.com/model/model.json';
buddhi.loadModel(modelUrl, dataUrl, callbackFunction);

function callbackFunction() {
console.log("model loaded!");
}
```

**modelUrl:** This is the URL where your trained model is located. You need to provided an **[Absolute URL](https://www.9thwonder.com/blog/the-difference-between-absolute-and-relative-urls-in-website-development)** here.

**dataUrl:** This is the URL where _model_metadata.json_ file is located. You need to provide a **[Relative URL](https://www.9thwonder.com/blog/the-difference-between-absolute-and-relative-urls-in-website-development)** here.

**callbackFunction:** Provide a callback function to be executed when the model is loaded. This is where you can start your chatbot work.

### Classify Sentences

```javascript
const sentence = 'What is your name?';
let answer = buddhi.classify(sentence);

console.log(answer);
```
Inputs

**sentence:** (_String_) Basically this is the user utterance/input.

Outputs

**answer:** (_Array<any>_) Returns an array of 3 elements

1.  _answer[0]: Bot response as String_
2.  _answer[1]: Name of Intent as String_
3.  _answer[2]: Confidence or the accuracy as float_

layout: default
