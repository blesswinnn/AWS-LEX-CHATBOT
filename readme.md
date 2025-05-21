
# 🤖 AWS Lex Chatbot – BankerBot

A hands-on project to build a chatbot using **Amazon Lex V2** that helps users check their balance and make transfers. Perfect for aspiring **Cloud Engineers** exploring AWS AI/ML services.

---

## 📌 Steps Overview

1. [Create a Lex V2 Bot](#create-your-bot)
2. [Configure Welcome Intent](#configure-welcome-intent)
3. [Test and Handle Fallbacks](#fallbackintent)
4. [Delete Resources to Avoid Charges](#delete-your-resources)
5. [Recap Your Learnings](#recap)

---

## 🚀 Create Your Bot

1. **Log in** to the AWS Console.
2. Navigate to **Amazon Lex**.
3. Ensure the URL contains `/lexv2/`. If not, click **Switch to the new Lex V2 console**.
4. Select **Create bot** → **Create a blank bot**.

![Create Bot](https://github.com/user-attachments/assets/f5cef820-c3a0-463b-82ba-64cda51767ea)

### Bot Configuration

| Field                  | Value / Option                                      |
|------------------------|-----------------------------------------------------|
| **Bot name**           | `BankerBot`                                         |
| **Description**        | *Banker Bot to help customers check balance & transfer funds.* |
| **IAM permissions**    | *Create a role with basic Amazon Lex permissions*   |
| **COPPA**              | `No`                                                |
| **Idle timeout**       | `5 minutes` (default)                               |
| **Language**           | `English`                                           |
| **Voice interaction**  | *Choose your favorite* (e.g., `Danielle`)           |
| **Confidence threshold** | `0.40` (default)                                |

> 💡 **What’s Intent Classification Confidence Threshold?**  
> This sets the minimum confidence (e.g. 40%) Lex must have to match an intent. Below this, it triggers a fallback.

![Settings](https://github.com/user-attachments/assets/0e72894a-ff3f-4d5d-b264-9ea425de15d5)

---

## 🧠 Configure Welcome Intent

1. When the bot is created, rename the default intent to `WelcomeIntent`.
2. Description: *Welcoming a user when they say hello*.

![WelcomeIntent](https://github.com/user-attachments/assets/c516c035-c510-49ca-9d90-eab9a0942f41)

### Add Sample Utterances

```
Hi  
Hello  
I need help  
Can you help me?
```

![Utterances](https://github.com/user-attachments/assets/2dedec1a-6ac0-4ac9-a7b0-c5079ed869b9)

3. Set the **Closing Response**:

```
Hi! I'm BB, the Banking Bot. How can I help you today?
```

![Closing Response](https://github.com/user-attachments/assets/d1dba670-a2cf-4ca1-a05e-49bd1c74c343)

4. Click **Save Intent** → **Build** → **Test**.

![Test Bot](https://github.com/user-attachments/assets/089857c4-e243-4411-b1b6-49f228bb95f7)

> ✔️ Defined utterances will always be recognized.
>
> ❓ Unknown phrases? Keep reading to handle them with **FallbackIntent**.

---

## 🧯 FallbackIntent

Amazon Lex uses `FallbackIntent` when the chatbot isn't confident in matching the user’s input.

### What to Do

1. In the left menu, select **FallbackIntent**.

![Fallback](https://github.com/user-attachments/assets/a385f88f-da81-4314-886a-a5dfa129389d)

2. Scroll to **Closing Response**, add these messages:

**Message 1**:
```
Sorry I am having trouble understanding. Can you describe what you'd like to do in a few words? I can help you find your account balance, transfer funds and make a payment.
```

**Message 2 (Variation)**:
```
Hmm, could you try rephrasing that? I can help you find your account balance, transfer funds and make a payment.
```

3. Add more variations for a more natural feel.
4. Click **Save Intent** → **Build** → **Test**.

![Test Fallback](https://github.com/user-attachments/assets/5d2016c0-26fb-4c3f-8495-e25ea411537f)

---

## ❗ Trouble Testing?

> **Error**: `Missing required key 'sessionId' in params`  
> 🛠️ Try the following:
- Refresh the chatbot window.
- Wait a minute and try again.
- If needed, close and reopen the test session.

---

## 🧹 Delete Your Resources

After testing, delete all resources to **avoid AWS charges**.

---

## 🧾 Recap

| ✅ Task | Description |
|--------|-------------|
| 🎯 Define basic intent | Responds to greetings like *hi* or *hello*. |
| 📝 Add sample utterances | Increases chatbot understanding range. |
| 🔁 Handle unknown inputs | `FallbackIntent` guides users if input isn't clear. |
| 💬 Add variations | Makes bot responses more natural. |
| 🧪 Build and test | Ensure the bot works as expected via the test chat. |

---

## 🧠 Documented With ❤️ by [NextWork]

> *Learning Cloud Engineering, one project at a time.*

---

### 📌 Hashtags (for LinkedIn Post)
```
#AWS #LexV2 #Chatbot #CloudEngineer #AI #MachineLearning #DevOps #AWSLex #Terraform #IAM #Serverless #DailyGrind #NextWork
```

