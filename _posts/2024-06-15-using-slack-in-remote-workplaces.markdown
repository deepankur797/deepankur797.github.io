---
layout: post
title:  "Using Slack Effectively in the remote workplaces"
date:   2024-06-15 14:38:52 +0530
categories: Culture
---

After the pandemic in 2020, many organizations underwent drastic changes in their operations. As the outside world became open to all again, some of those operational practices either evolved or changed permanently. One such practice was the workplace setting itself. A huge set of companies, especially in the Information Technology sector, maintained their practice of Work From Home (WFH) either by going remote first or having a hybrid culture.

This had some underlying effects on the day-to-day working of the employees. The first and foremost observable change was the way of communication. I categorize this as the biggest change because in the office conversations were synchronous, you have the other person present in front of you, but now the communication becomes asynchronous because we don’t know whether the other person is focused on some important task or wants to have a continuous conversation over text.

In this blog post, I tried to share tips on how to effectively leverage async conversation tools, such as Slack, Teams, emails, or any other communication tool your organization might be using. In this blog post, we are going to be focused on Slack, but the same principles can be applied to other tools as well.

## Staying in the Zone

Have you ever experienced a loss of track of time because you were so focused on doing an activity? That state of mind is called a flow state or being in the zone. Time feels like it has slowed down. Your senses are heightened. You are at one with the task at hand, as action and awareness sync to create an effortless momentum. This is the time in which you are most efficient and creative. A message on Slack with the classic “Knock Brush” sound of a Slack notification can break this cognitive state, as now the person needs to switch the context to and fro between two tasks, especially if the Slack conversations are not streamlined. More on this state can be read [here](https://sre.google/sre-book/dealing-with-interrupts/#cognitive-flow-state-yDsrIgHQSecondly).

One should update their Slack status and let others know that he/she might not be readily available to answer texts before going into the flow state. It is highly recommended that you pause your notifications while trying to focus on the task at hand. In case of an emergency, Slack reminds the sender that the receiver’s notifications are paused with “Do you want to notify anyway?” There are applications like “Clockwise” that can help you find these time slots where you can have focused work time.

## Slack etiquettes

Some people might not have used Slack, which is a pretty common problem as the tool is still growing, although it would be safe to say that its popularity has risen exponentially in the past. But nothing to worry about [Slack video tutorial](https://slack.com/intl/en-gb/help/articles/360059976673-Slack-video-tutorials) can help you get started quickly.


### Avoid Naked Pings

We all like to be polite, and as a result, while messaging we usually start with less informative messages or greetings like “Good Morning”, “hi”, “Hello” etc. Our goal should be to reduce interruptions because the recipient of this message is as busy as you. Make your messages more informative by adding context to the same message for example you can say

```
 “ Hello John,
Can we do a pair programming session tomorrow at 10 am on problem X ?”

```
```
Tip for Slack users, to draft a multiple paragraph message use shift+return
```


### Use Channels for communications

Slack works better if the organizational culture promotes the use of the channels instead of the private DMs. Using the channels over the DM(direct message) chats has numerous advantages. 

* Other team members can also contribute their opinions on channels, but DM can lead to various information silos.
* One doesn’t need to explain the context behind something as the whole discussion can be read by new users.
* New joiners can be pointed to the old decisions made, rather than explaining to them again why we do something in a particular way. 

We should also avoid the use of private channels for the same reasons. Only use them whenever sensitive information is being discussed. No matter what kind of information is being discussed, never use Slack to share credentials instead use password managers like 1Password for that.

Use the `@<username>` wisely, and only when it is urgent to get somebody’s attention or the size of the channel is too big. At all costs try to avoid using `@here` or `@channel` these are the most annoying notifications and should be only used if something is burning on fire. 

Keep your team informed about the purpose of some specific channels, For example, you can set a description for the intended use of the channel or create a documentation for new joiners for some common Slack Channels and their effective use. 


### Use Threads Effectively in the conversations

While using channels is the most effective way of communication on Slack it can get messy especially if the conversation or discussion around a single topic isn’t being carried out in the thread. 

Leveraging threads can tackle this issue, keeping your discussion organized. There are other advantages for threads as well


* Only people involved in the discussion get notified
* Other people can turn on notifications about a particular thread if they want to get notified. 
* Easier to find past conversations as well. 

![Slack Threads](../assets/images/threads.png)

In the above example all the conversation related to maintenance happened under a single thread. This makes it less clutered

### Replace short messages with Emojis

Emojis are something that really differentiates an email-like communication system from a messaging-based one. Emojis can be effectively used to convey a lot of things for example

![Slack Emojis](../assets/images/emojis.png)
*Image Credits: [Slack](https://slack.com/intl/en-gb/blog/collaboration/etiquette-tips-in-slack)*

Use these emojis to their power and say more with less typing. You can even set up simple workflows with these emojis.

## Add details in your messages

Finally, you have everything streamlined in your conversation practices, the final missing piece of the puzzle is your message itself. Your message should be detailed enough so that the reader gets the full picture of the question you are asking, the problem you are describing or an announcement you are making.

The following points can help to make your messages more detailed

### Try to Specify why part of the question

This is the most common follow-up question you can answer about your message. Example

```
Deepankur:
    Hey James,
    Can you give me access to X repository?
```

Now James is wondering why he needs the access there. A better message would be

```
Deepankur:
    Hey James,
    To resolve the access-request issue of the developers, can I have access to the repository X? As I have to …
```

### Don’t Assume

![XKCD Comic](../assets/images/xkcd.png)

*Image Credit: [xkcd.com](https://xkcd.com/1860/)*

As multiple teams collaborate on Slack not everyone has the same background so don’t assume and know your audience to whom you are messaging. Tailor your message accordingly for example, while messaging your technical teams, you might want to add more tech-oriented things, whereas, with your sales and marketing teams, you want to omit design considerations and tailor your message to customer/team requirements.

### Add more context and add a TLDR

While adding the context, the messages can become longer, in such cases adding a TLDR could be very much beneficial. This can give readers an overview and help them decide whether they want to read more context or not. This can also help them decide the urgency of the message in some cases they want to reply immediately or whether they want to come back to this later.

### Mention what you want to get out of the communication

Make sure that your messages are actionable, i.e. they state the clear purpose of why you are communicating this information

```
Deepankur: I am on leave tomorrow. 
James: Okay.
```

```
Deepankur: Hello James, I am on leave tomorrow can you please approve the leave request?
```

## Conclusion

I hope you find these suggestions useful and this will help you to streamline your Slack communications.  This is something an individual keeps on working on, as asynchronous communication always has some room for improvement. Even to this day while writing this blog, I cut corners sometimes here and there, but the important part is to keep on improving. 


## Refrences

1. https://www.headspace.com/articles/flow-state
2. [Google SRE Book](https://sre.google/sre-book/dealing-with-interrupts/#cognitive-flow-state-yDsrIgHQSecondly)
3. https://slack.com/intl/en-gb/blog/collaboration/etiquette-tips-in-slack
4. https://blogs.gnome.org/markmc/2014/02/20/naked-pings/
5. [Async Communications](https://www.infracloud.io/blogs/async-communication-remote-work/)
