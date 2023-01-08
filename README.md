# alexa-apl-sequentially-play-speech-video-speech
This repo is an example integration showing how you can use in your Lambda function the APL Ninja sample that allows you to sequentially play text to speech, video and then text to speech again (https://apl.ninja/MavPeri/sequentially-play-speech-video-and-speech-again-eeea).


The lambda function included in this example is based on the sample hello world lambda function you get when you create a new custom skill in the Alexa Developer Console.


The ```LaunchRequestHandler``` of the lambda function has been modiifed to inflate the APL document and execute the sequential commands that play text to speech, a short sample video and then text to speech again. See the file  ```code/lambda/index.js``` to see where the datasources and sources are defined and how they are passed to the APL document. 

### Using the APL document saved by the Alexa APL authoring tool###
In this example  the APL json document is part of this repo at ```code/lambda/APL/speechvideospeech.json```. 

If you wish to include the APL document saved in the APL authoring tool, you will need to change the document to ```"type": "link"``` instead of using ``` document: require('./APL/speechvideospeech.json'),```

Specifically change 

```

const createDirectivePayload = (aplDocumentId, dataSources = {}, tokenId = "myTokenID") => {
    return {
        type: "Alexa.Presentation.APL.RenderDocument",
        token: tokenId,
        document: require('./APL/speechvideospeech.json'),
        datasources: datasource,
        sources: sources
    }
    
};

```

*to* 

```

const createDirectivePayload = (aplDocumentId, dataSources = {}, tokenId = "myTokenID") => {
    return {
        type: "Alexa.Presentation.APL.RenderDocument",
        token: tokenId,
        document: {
            "src": "doc://alexa/apl/documents/YOUR_OWN_APL_DOCUMENT_NAME_HERE",
            "type": "Link"
        },
        datasources: datasource,
        sources: sources
    }
    
};

  "document": 

```







