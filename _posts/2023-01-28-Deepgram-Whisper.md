---
title: Streamlining Audio Transcription | Using the OpenAI Whisper Model in a Single Post Request
date: 2023-01-28 00:00:00 
categories: [Technology, Artificial Intelligence]
tags: [audio transcription, openai, whisper]
---

Artificial Intelligence is currently applied in all fields. It's been wild and the development is tremendous. One of the interesting applications of AI is speech recognition. **Automatic speech recognition** (ASR) is a technology that allows machines to understand and interpret spoken language. Nowadays it can be seen in most places. This technology is used in a variety of applications, such as virtual assistants, language translation services, and voice-controlled devices. Some common examples include Siri, Google Assistant, and Amazon Alexa.

Over these years, there's a lot of research is going on in this domain. Deepgram is one of the [Deepgram](https://deepgram.com/) is an AI speech platform and they have [Completes $72M Series B Round to Define the Future of Speech Understanding.](https://blog.deepgram.com/deepgram-72-million-series-b-defines-future-of-ai-speech-understanding/)

[OpenAI](https://openai.com/), an AI research company that you may have heard about through ChatGPT also released an open-source model for Automatic Speech Recognition called **Whisper**. Want to explore it? Check out [Exploring OpenAI's Whisper](https://aadarshkannan.hashnode.dev/exploring-openais-whisper).

Deepgram made it easier for us to access Whisper It is now available for anyone to use through Deepgram without the need for an account.

All in this simple POST request by sending the audio.

```bash
curl --request POST \
  --url 'https://api.deepgram.com/v1/listen?model=whisper' \
  --header 'Content-Type: application/json' \
  --data '{
	"url": "https://static.deepgram.com/examples/Bueller-Life-moves-pretty-fast.wav"
}'
```

#### What's happening in the above POST request? 

The above curl command sends an HTTP POST request to the Deepgram API with a URL parameter of "model=whisper" and a request body containing a JSON object with the URL of the audio file that you want to analyze. In response, Deepgram will process the audio file and return the results. The results will include the audio transcription and other information about the audio, such as the language, models used, and confidence scores for each individual word.

To conclude, Speech recognition is just getting started. **Let the voices be heard and understood!**

Your support means a lot to me. Thank you for reading my article.
