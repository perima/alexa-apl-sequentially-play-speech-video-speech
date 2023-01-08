# alexa-apl-sequentially-play-speech-video-speech
This repo is an example integration showing how you can use in your Lambda function the APL Ninja sample that allows you to sequentially play text to speech, video and then text to speech again (https://apl.ninja/MavPeri/sequentially-play-speech-video-and-speech-again-eeea).


The lambda function included in this example is based on the sample hello world lambda function you get when you create a new custom skill in the Alexa Developer Console.


The ```LaunchRequestHandler``` of the lambda function has been modiifed to inflate the APL document and execute the sequential commands that play text to speech, a short sample video and then text to speech again.




