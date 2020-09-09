---
author: Krunal Kapadiya
title: NLP in ML-Kit
date: 2020-05-26    
description: NLP in MLKit
math: true
---


Hello, welcome to this article. In this article, I will discuss NLP API of ML-Kit and common details of cloud and firebase and where to start with ML-Kit.

# Introduction

Firebase first initiated in 2011 by two tech-professionals James Tamplin and Andrew Lee. Goal to create firebase is to provide API that synchronizes application data across iOS, Android and web services, the first product of firebase is Firebase Real-time Database. Later on, in 2014, it is acquired by Goolge. As of March 2020, Firebase platform has 19 products, which are used by more than 1.5 millions of apps. ML-Kit is announced in Google IO 2018. The main focus area for this API is to use the Machine learning pre-trained model on cloud and on-device in smaller devices. It also supports custom models. As in the cons part, while using a custom model, application size increase largely. We will discuss in a later part how to reduce app size.

> Fun Fact: DialogFlow and Firebase born in 2011 :)

This article includes the vision, natural language of MLKit and common steps that needs to follow before publishing application in production.

# NLP in ML-Kit

1.  **Language Identification**

This API serves to identify unknown language. We can use this API in two ways,

-   Identify which language only, one single output will be there
-   Identify language with possible languages (Returns array with probabilities)

This library is common for all listed library below,

implementation 'com.google.firebase:firebase-ml-natural-language:22.0.0'implementation 'com.google.firebase:firebase-ml-natural-language-language-id-model:20.0.7'

Now, create instance of  `FirebaseLanguageIdentification`

FirebaseLanguageIdentification languageIdentification =FirebaseNaturalLanguage.getInstance().getLanguageIdentification();

Now, all set to have use Language Identification API.

Input text is-> Hola

With  `identifyPossibleLanguages(“Hola”)`  we have output `[ES- 0.983427]`

With  `identifyLanguage(“Hola”)`we have output `Hola-ES`

## 2. Translate Text

This API use to translate text from unknown languages from camera, image or from video.

To use this API Android Studio will need to add following gradle file,

implementation 'com.google.firebase:firebase-ml-natural-language-translate-model:20.0.7'

We are creating  `FirebaseTranslator`  instance by adding source and target languages, which looks like below.
```
FirebaseTranslatorOptions options = new FirebaseTranslatorOptions.Builder()  
.setSourceLanguage(FirebaseTranslateLanguage.EN)  
.setTargetLanguage(FirebaseTranslateLanguage.DE)  
.build();final FirebaseTranslator englishGermanTranslator =FirebaseNaturalLanguage.getInstance().getTranslator(options);
```
Now, one more step is remaining, what it is any guess?

In this API, we need to download the model. Currently, ML-Kit supports translation for 59 languages. All models have downloadable size up to 60 to 90 MB. Once you download the model, translation API will work smoothly in offline mode.

To translate in non-English languages, English language performs as mediator which causes in the lower accuracy in the translated text.

You can create a translation model offline, but for that, you will need lots of data, then you need to perform many operations cleaning text, getting sentence into the main verb, combining similar words, generating word-cloud and many operations. But with MLKit, you can use translation with couple of lines with best translation accuracy. So simple isn’t it!!

## 3. Generate Smart Reply

From the last 10 chat in conversation, predict the best suggestion use this API. Many users have seen this API, in chatting apps.  _This API supports only the English language._ Also, it won’t provide a result when there will be any sensitive outcome.

Generate Smart reply API have following,

implementation 'com.google.firebase:firebase-ml-natural-language-smart-reply-model:20.0.7'

And below is the callback,
```
FirebaseNaturalLanguage.getInstance()  
.getSmartReply().suggestReplies(chatHistory).continueWith(new Continuation<SmartReplySuggestionResult, List<SmartReplySuggestion>>() {  
@Overridepublic List<SmartReplySuggestion> then(@NonNull Task<SmartReplySuggestionResult> task) {return task.getResult().getSuggestions();  
}});Sender: HiSmartReplySuggestion{text=😊, confidence=0.10804383}SmartReplySuggestion{text=How are you?, confidence=0.04037162}SmartReplySuggestion{text=Okay, confidence=-0.050458048}That’s It!!!
```
----------

To reduce APK size, build an APK file as in Android App Bundle, by doing it, Google Play will generate APK for screen density, CPU architecture, and languages.

To reduce APK size, build an APK file as in Android App Bundle, by doing it, Google Play will generate APK for screen density, CPU architecture, and languages.

----------

Also, MLKit provides APK for both 32 bit and 64 bit, if app only support 32 bit then strictly use 64 bit. We can make build for 32 bit when needed as shown in below code snippet.

android {defaultConfig {ndk {// Don't package arm64-v8a or x86_64abiFilters 'armeabi-v7a', 'x86'}}}

I have created NLP-MLKit library for reference. Clone this repository, add google-services.json file and run the application.

[](https://github.com/krunal3kapadiya/NLP-ML-Kit)

## krunal3kapadiya/NLP-ML-Kit

### Sample application to demonstrate NLP API of Firebase ML-Kit — krunal3kapadiya/NLP-ML-Kit

#### github.com

----------

# You should know before you start with MLKit

-   Image labelling, onDevice model supports 400 labels and onCloud model support 10000 labels.
-   Barcode scanning supports 9 types of results to save (e.g, WiFi, Driving Licence, Contact number etc). So application can behave intelligently and it support for all types of barcodes. (// TODO add image for barcode)
-   AutoML use to classify images with labels.
-   For Flutter developers, there are FlutterFire plugin available for ML vision APIS

At last, I will say that ML-Kit API saved tons of work for developers who want to add artificial intelligence in their application.

# Where to start and references

-   [https://heartbeat.fritz.ai/](https://heartbeat.fritz.ai/)
-   [https://firebase.google.com/docs/ml-kit](https://firebase.google.com/docs/ml-kit)
-   [https://github.com/firebase/quickstart-android/tree/master/mlkit](https://github.com/firebase/quickstart-android/tree/master/mlkit)
-   [https://medium.com/google-developer-experts/exploring-firebase-mlkit-on-android-barcode-scanning-part-three-cc6f5921a108](https://medium.com/google-developer-experts/exploring-firebase-mlkit-on-android-barcode-scanning-part-three-cc6f5921a108)
-   [https://github.com/firebase/mlkit-material-android](https://github.com/firebase/mlkit-material-android)
-   [https://github.com/googlecodelabs/mlkit-android](https://github.com/googlecodelabs/mlkit-android)

Now, I am now concluding this article. Hit Like and share if you like this article. You can give me feedback for this article on my twitter id:-

[https://twitter.com/krunal3kapadiya](https://twitter.com/krunal3kapadiya)

Happy Learning :P