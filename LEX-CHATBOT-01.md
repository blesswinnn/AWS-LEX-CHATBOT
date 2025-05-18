# AWS-LEX-CHATBOT

- Log in to the AWS console.
- Navigate to Amazon Lex (type Lex into the search bar of your Console).
- Check your URL in your web browser - does it say ...console.aws.amazon.com/lexv2/...?
- If you're not seeing "lexv2" in your URL, click on Switch to the new Lex V2 console link in your left-hand menu.
- Select Create bot.
- Select Create a blank bot.

![image](https://github.com/user-attachments/assets/f5cef820-c3a0-463b-82ba-64cda51767ea)

- For Bot name, enter BankerBot
- For Description, enter Banker Bot to help customer check their balance and make transfers.
- Under IAM permissions, select Create a role with basic Amazon Lex permissions.

![image](https://github.com/user-attachments/assets/325b3543-779f-4a5a-bd97-2884bd5f47a1)

- We'll be using it to call another service called Lambda later!
- Under Children’s Online Privacy Protection Act (COPPA), select No.
- Under Idle session timeout, keep the default of 5 minutes.

![image](https://github.com/user-attachments/assets/ab949d72-0c29-474e-a516-464b285c4855)

- Select Next.
- Keep the language as English so you can explore Lex's full set of features in this project
- Under Voice interaction, click on the dropdown that says Danielle
- Click around different voice options to choose your favorite one!
- For Intent classification confidence score threshold, keep the default value of 0.40.

![image](https://github.com/user-attachments/assets/0e72894a-ff3f-4d5d-b264-9ea425de15d5)


`💡 What is intent classification confidence score threshold?
When you're using Amazon Lex to build a chatbot, this threshold is like a minimum score for your chatbot to confidently understand what the user is trying to say.
Setting this to 0.4 means that your chatbot needs to be at least 40% confident that it understands what the user is asking to be able to give a response.
So if a user's input is ambiguous and your chatbot's confidence score is below 0.4, it'll throw an error message.
`
# Create your first intent

- When your bot is created, you will automatically see a page called Intent: NewIntent
- Let's change the name!
- Under Intent details, enter WelcomeIntent for the Intent name.
- Add the description Welcoming a user when they say hello.

![image](https://github.com/user-attachments/assets/c516c035-c510-49ca-9d90-eab9a0942f41)

- Scroll down to the Sample utterances panel.
- Click the Plain Text button.
- Copy the text below,
```
  Hi
  Hello
  I need help
  Can you help me?
```
![image](https://github.com/user-attachments/assets/2dedec1a-6ac0-4ac9-a7b0-c5079ed869b9)

- Click back to the Preview button to see these utterances in chat form.
  ![image](https://github.com/user-attachments/assets/2b7edf6a-47aa-47b9-8c79-75940a006c58)

- Scroll down to Closing response, and expand the arrow for Response sent to the user after the intent is fulfilled.
- In the Message field, enter the following message:
```Hi! I'm BB, the Banking Bot. How can I help you today?```
![image](https://github.com/user-attachments/assets/d1dba670-a2cf-4ca1-a05e-49bd1c74c343)

- Choose Save intent.
- Choose Build, which is close to the top of the screen.
- This can take 30 seconds
- choose test option

![image](https://github.com/user-attachments/assets/089857c4-e243-4411-b1b6-49f228bb95f7)

- The ones that you have literally defined in your Utterances section will definitely work.

# But what about other utterances?
` 💡 How does my chatbot respond to these user inputs?
The first three are successfully recognized - Amazon Lex is able to use its ML techniques to match what you have said against your utterances.
But the last two fail, resulting in an Intent FallbackIntent is fulfilled response - meaning Amazon Lex doesn't quite recognize your utterance.`

`💡 What is FallbackIntent?
Remember the intent classification confidence score threshold, and how it's been set to 0.4?
If your chatbot has a confidence score below 40% for all the intents you've defined (in our case, it's just the WelcomeIntent for now), the FallbackIntent is triggered.
Think of it as a custom error message that your chatbot will use to tell the user it doesn't understand their input.`

- In your left hand navigation panel, choose FallbackIntent.
![image](https://github.com/user-attachments/assets/a385f88f-da81-4314-886a-a5dfa129389d)

- Scroll down to Closing responses.
- Expand the arrow for Response sent to the user after the intent is fulfilled.
- In the Message field, add the following text:‍
  ```Sorry I am having trouble understanding. Can you describe what you'd like to do in a few words? I can help you find your account balance, transfer funds and make a payment.```
- You'll notice another arrow next to the label Variations - optional.
- Expand the arrow.
- Enter the following text:
  ```Hmm could you try rephrasing that? I can help you find your account balance, transfer funds and make a payment.```
- Add another variation! What is another response that the chatbot could use to get clarification if it doesn't understand the user's intent?
- Choose Save intent.
- Choose Build
- Choose Test.

![image](https://github.com/user-attachments/assets/5d2016c0-26fb-4c3f-8495-e25ea411537f)

`🙋‍♀️ I'm getting an error
Does your error say Missing required key 'sessionId' in params?
That usually means your bot needs a refresh or some time until it's ready for testing.
Select the refresh button at the top of your chatbot's chat window.
If you're still seeing the error, wait another minute before sending another message.
If you're still seeing the error, close this window and select Build and Test again.`

# Delete Your Resources
Make sure you delete all your resources to avoid getting charged. This is a super important task for every single project you set up.

# RECAP

- 🎯 Define a basic intent: You configured a basic intent in Amazon Lex to control how your chatbot responds to user inputs.
- 📝 Create lists of utterances: You compiled a list of sample utterances that trigger different intents, which means your chatbot can recognize different user phrases and respond.
- 🛠️ Handle failures with FallbackIntent: You edited FallbackIntent to handle unrecognized or poorly understood user inputs.
- 🔁 Define variations to provide semi-random responses: You designed a MessageGroup of variations, which makes your chatbot sound more natural and conversational.
- 🧪 Build and test your bot: You tested your bot's setup in both text and voice formats. This comprehensive testing helps you confirm that your chatbot is ready for real-world interactions!

DOCUMENTED WITH THE HELP OF NEXTWORK.
