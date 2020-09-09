---
author: Krunal Kapadiya
title: Actions On Google Are You Stuck?
date: 2019-02-09    
description: Actions On Google Are You Stuck?
math: true
comments: true
---


Hi folks, I’m writing this article to cover various points which needs to be taken care of while submitting your Actions (Action for Google Assistant) for review in order to avoid rejection. So without wasting time lets Start :-)

This is the story when I was developing and publishing ML Wordtoit — Chatbot that helps with vocabularies of Machine learning. I got this email when I first submitted my agent.

![Image for post](https://miro.medium.com/max/60/1*6g5h5Gzz562hOZEgvoGN_g.png?q=20)

![Image for post](https://miro.medium.com/max/1005/1*6g5h5Gzz562hOZEgvoGN_g.png)

I improved and passed it by the following steps…

## #1. Don’t let mic open

If you have chosen Dialogflow as your building action then make sure your using suggestion chips in order to let the user know that mic is still open or action is waiting for your next instruction. In case you do not want any suggestion chips assuming it is the end of conversation do not forget to close the mic by toggling the button on placed at the bottom of response tab.

While making intent and conversation, there may be chances that you forgot to add fallback intent/close the conversation. This is bad conversation flow, you are not leading the conversation. Add response by adding fallback intent or close the conversation. It will leave the mic open for an agent, it’s an incomplete conversation. So close the mic. You can close mic in this way:-

1.  In intent conversation: Enable the checkpoint for ending a conversation.

![Image for post](https://miro.medium.com/max/60/1*tb6MmEuxEid5GlCzWTF8lg.png?q=20)

2. With the help of the node, write  `conv.close(‘Your message’)`  it will close your conversation.
```
function fallback(agent) {  
 let conv = agent.conv();  
 conv.close(‘Good bye’);  
}
```
## #2. How to choose Agent’s name

You also get rejected by the name of your agent. Agent names must differ from other agents name in the  [Google Actions store](https://assistant.google.com/explore). It does not contains a single word, person name and places name. Brand name, unique name, and companies name sometimes valid on request.

> In alpha/beta release you can pass your agent with single name, but be aware ready you will get rejection in production release.

## #3. Invocation

How to call your agent? Do I need to call your agent name every time? Invocation is the callback that will open up your agent. Use different ways to create your agent. Know what informations your agent is providing based on that choose the invocation. If your agent gives information about the weather then you can use the following invocation to create the agent.

— Hey, Google I want to know the weather.

— Hey Google, what's the update in weather

— Hey Google, let me talk to (Your weather app name)

Also, don’t forget to read invocation  [checklists](https://developers.google.com/actions/discovery/checklist).

Lastly, I successfully published my agent. Cheers.

![Image for post](https://miro.medium.com/max/60/1*rYt4tSpNJKVjPKP8o2hRYw.png?q=20)

![Image for post](https://miro.medium.com/max/998/1*rYt4tSpNJKVjPKP8o2hRYw.png)

I covered almost all the points that are missing in publishing agent. You can DM me problems that are not listed in this article. You can check  [ML Wordtoit](https://bit.ly/mlwordtoit)  and DM me if for any update. Create your AoG app faster with better actions.

All the best. Thanks for reading it.

----------

> Thanks to  [Kamal Vaid](https://medium.com/u/ac8a5902947b?source=post_page-----5adfdf9a6a9f----------------------)  for reviewing this article and adding useful details in it. :)

_~If this article helps you to pass your agent in production, click 💚 below so more people can see it. Also, follow me on_ [_Twitter_](https://twitter.com/krunal3kapadiya) _or_ [_Medium_](https://medium.com/@krunal3kapadiya/)_, so you get updates regarding my upcoming articles~_