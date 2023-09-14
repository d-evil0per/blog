---
title: "How to Read Emails Using Python?"
seoTitle: "How to Read Emails Using Python?"
seoDescription: "Email Alert with a voice in python."
datePublished: Mon Jan 31 2022 00:03:12 GMT+0000 (Coordinated Universal Time)
cuid: ckz1xhwgv0df5mjs15romc33a
slug: how-to-read-emails-using-python
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1643585329054/H3Jlmm-Ic.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1643587328149/RrDHZhchO.jpeg
tags: python3

---

# How to Read Emails Using Python.

As we know Python is being used widely across every domain. And I bet, every programmer had thought about building some kind of virtual assistance(let's call it **VA**) after watching "**Iron Man Movie**". In **VA** we add logic to do different tasks like opening some application, searching on the web, solving mathematical calculations, weather updates, Reminders, To-dos and this can go on and on. So, You might be thinking...

![Panchcyat-Memes-point-pe-aa-na-sidha](https://drive.google.com/uc?export=view&id=1IXnN9c-h7k6bWbSnEoSUSnAEnEkmIPqG)


​							<!--Come Straight to the Point-->

**Okay, But Hindustani Bhau has something to say to you!! ** 


![ruku jara bhau](https://drive.google.com/uc?export=view&id=1xIE70M38f1GdmFbh64UhYRz1-WAJYIqh)

​										<!--Please be patient-->

We can add an Email Reader as well in your **VA**.To do so we need to first understand these few things mentioned below.

- **Libraries  to communicate with email services providers**
- **A purpose like downloading Bills, Tracking  shopping orders, data analytics, reminders, follow-ups,auto-replies and much more dependence on the need**

Let's get started with some technicalities and as an example will serve one purpose through python. Excited Right??

![abhi-maza-ayega-na-bhidu](https://drive.google.com/uc?export=view&id=1zYN2fSpdwTDWaBxyJ3aV8u_WV9dihJDP)  

​									<!--Now it's going to be fun-->

### Libraries: [imap_tools](https://github.com/ikvk/imap_tools) or [imaplib](https://docs.python.org/3/library/imaplib.html) 

#### [imap_tools](https://github.com/ikvk/imap_tools) 

The easiest tool I've found for reading emails in Python is [imap_tools](https://github.com/ikvk/imap_tools). It has an elegant interface to communicate with your email provider using IMAP (which almost every email provider will have).

First, you access the MailBox; for which you need to get the IMAP server and login credentials (username and password). You should be able to find this in your email provider's help or settings (e.g. [here's a guide for Gmail](https://support.google.com/a/answer/9003945)).

```python
from imap_tools import MailBox, AND

# Server is the address of the IMAP server
mb = MailBox(server).login(user, password)
```

Then you can search for messages based on [RFC 3501 Search Criteria](https://tools.ietf.org/html/rfc3501#section-6.4.4). There are lots of examples in the [imap_tools README](https://github.com/ikvk/imap_tools#search-criteria); you can search based on the sender, subject, text, date, and others.

```python
# Fetch all unseen emails containing "xyz.com" in the from field
# Don't mark them as seen
# Set bulk=True to read them all into memory in one fetch
# (as opposed to in streaming which is slower but uses less memory)
messages = mb.fetch(criteria=AND(seen=False, from_="xyz.com"),
                        mark_seen=False,
                        bulk=True)
```

Then you can access things like the subject, from address, date, and text and HTML content using [simple attributes](https://github.com/ikvk/imap_tools#email-attributes).

```python
files = []
for msg in messages:
    # Print form and subject
    print(msg.from_, ': ', msg.subject)
    # Print the plain text (if there is one)
    print(msg.text)
    # Add attachments
    files += [att.payload for att in msg.attachments if att.filename.endswith('.pdf')]
```

It also handles [actions](https://github.com/ikvk/imap_tools#actions-with-emails) on emails such as flagging as seen, moving, and deleting messages.

#### [imaplib](https://docs.python.org/3/library/imaplib.html)

Python has the built-in [imaplib](https://docs.python.org/3/library/imaplib.html) for IMAP and [email](https://docs.python.org/3/library/email.html) for processing emails. Unfortunately, they're quite a low level and require a bit more work to use than imap_tools.

```python
import imaplib
import email

mb = imaplib.IMAP4_SSL(server)
rv, mesasge = mb.login(user, password)
# 'OK', [b'LOGIN completed']
rv, num_emails = M.select('Inbox')
# 'OK', [b'22']

# Get unread messages
rv, messages = M.search(None, 'UNSEEN')
# 'OK', [b'21 22']

# Download a message
typ, data = M.fetch(b'21', '(RFC822)')

# Parse the email
msg = email.message_from_bytes(data[0][1])
print(msg['From'], ":", msg['Subject'])

# Print the Plain Text (is this always the plain text?)
print(msg.get_payload()[0].get_payload())
```



Once you go through these libraries you will get an idea about how to serve a specific purpose according to your requirement. Then you will be like...

![mai-merko-sab-ata-hai-mai-expert-hu](https://drive.google.com/uc?export=view&id=1ghq-WPzI0m4P2BR6erXB-o92_qdR2KPJ)

​						<!--I know everything, I'm an expert!!-->



### Purpose:  Let's make an Email Alert with a voice in python.

![to kar na](https://drive.google.com/uc?export=view&id=1ENkdTXFXXT7XTV162egCo84aN93t_mtX)

​													<!--Then, Do It-->

In order to make a solution for this purpose we have to do certain things as listed below:

- Install required Libraries such as 
  - **[GTTS (Google Text to Speech)](https://pypi.org/project/gTTS/)** : for text to speech conversion.   
  - **[playsound](https://pypi.org/project/playsound/)** : to play a audio files.
- Fetch the latest unread emails from the email provider.
- convert the text from email to Speech using **GTTS** and finally play it using **playsound** 

Let's import all the required libraries we need in this script.

```python
from imap_tools import MailBox,AND
import getpass
import json
from gtts import gTTS
import playsound

```

In the above, we have used the **[getpass](https://docs.python.org/3/library/getpass.html)** module to get the “login name” of the user. **[json](https://www.askpython.com/python-modules/python-json-module)** to read the **mailconfig.json** that holds the user credentials and server configs.



```json
{
    "mail":
    {
        "ORG_EMAIL":"@example.com",
        "FROM_EMAIL":"abc",
        "FROM_PWD":"password",
        "SMTP_SERVER":"imap.example.com",
        "SMTP_PORT":"993"
    }
}
```

**[imap_tools](https://github.com/ikvk/imap_tools)** for communication to the email service provider such as gmail,outlook etc.

Now Let's create two functions, **read_email_from_email(username,configdata)** that takes two parameters **username**(logged in user) and **configdata**(data from mailconfig.json) for communicating with the email provider and **speak(text)** that takes single parameter as String to convert it to speech.

```python
def speak(text):
    tts = gTTS(text, lang='en') #gtts API to convert text to speech
    tts.save("output.mp3") #saving as the audio file
    playsound.playsound('output.mp3') #playing from audio file
```

```python
def read_email_from_email(username,configdata):
    ORG_EMAIL   = configdata['mail']['ORG_EMAIL']
    FROM_EMAIL  = configdata['mail']['FROM_EMAIL'] + ORG_EMAIL
    FROM_PWD    = configdata['mail']['FROM_PWD']
    SMTP_SERVER = configdata['mail']['SMTP_SERVER']
    mail = MailBox(SMTP_SERVER).login(FROM_EMAIL, FROM_PWD)
    messages = mail.fetch(criteria=AND(seen=False),mark_seen=True,bulk=True)
    
    msg=list(messages)
    count=len(msg)
    if count>0:
        text=username+", You have an Email From "+msg[0].from_+",with a Subject Saying "+msg[0].subject
        print(text)
        speak(text)
    
    else:
        print("You Don't have any new emails!!")
        speak("You Don't have any new emails")


```

In **read_email_from_email**, we are connecting the Mail server using **Mailbox** with user credentials. With **fetch(criteria=AND(seen=False),mark_seen=True,bulk=True)** we are fetching all emails that are **unseen** in **bulk** and also **marking them as seen**. Then we are just creating a String using **From Email** and **Subject**. When we run this script it will read the latest email and also mark it as **Read**. for example:

[![output](https://drive.google.com/uc?export=view&id=1cOP9htfwP843fg3L0UGqBHX_qzAE8Qwl)](https://drive.google.com/uc?export=view&id=1w4ZCraficJzMBiI2A-b8oEJ2dlzz6Vbz)


For just the demo, I have just used the first fetched message. But you can play around with it and process those data according to your requirement.

I hope this article helped you to get familiar with how to read emails using python. and I wish your reaction would be like this.

![mazza aya](https://drive.google.com/uc?export=view&id=1Q0m4zo9ICQ7O2wUawqmOnbXy9Rr3hgh4)

​													<!--I enjoyed It!!-->



Stay tuned for more exciting blogs related to How to-dos and Connect with me on my social handles to share the feedback or you can also comment your thoughts, I would love it. 

![Khatam tata bye bye](https://drive.google.com/uc?export=view&id=1w1lToE1m3aHHNW1QSUzbgUdzsjdq4Qzy)







