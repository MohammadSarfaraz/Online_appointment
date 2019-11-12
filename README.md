# Online_appointment using Rasa X
Online appointment using [RASA X](https://rasa.com/docs/rasa/user-guide/installation/) to take an appointment with the consultant doctor and take feedback from there meeting.I am using  rasa as a platform to create dialogue management and spacy for training the module.

Here are some example given below--

![screenshot](https://github.com/MohammadSarfaraz/Online_appointment/blob/master/Screenshot%20from%202019-11-12%2015-40-52.png)

![Markdown logo](https://github.com/MohammadSarfaraz/Online_appointment/blob/master/Screenshot%20from%202019-11-12%2015-52-32.png)

Steps to install rasa x-->

![rasa](https://d2z6c3c3r6k4bx.cloudfront.net/uploads/event/logo/1077848/2ed953fb073b5e91df6a2e4e10b20578.png)

1.pip install rasa-x --extra-index-url https://pypi.rasa.com/simple


2.rasa init --no-prompt

The above command rasa init will create all necessary files which are required for creating rasa chatbot like domain.yml,credentials.yml,data/stories.md,data/nlu.md.

You will build a simple, friendly assistant which will ask how you’re doing and send you a fun picture to cheer you up if you are sad.

Here are the example below 
     
 ![Markdown logo](https://github.com/MohammadSarfaraz/Online_appointment/blob/master/Screenshot%20from%202019-11-12%2016-11-42.png)

3. The glossary contains an overview of the most common terms you’ll see in the Rasa documentation.

1. Create a New Project
2. View Your NLU Training Data
3. Define Your Model Configuration
4. Write Your First Stories
5. Define a Domain
6. Train a Model
7. Talk to Your Assistant

4. Write Your First Stories
At this stage, you will teach your assistant how to respond to your messages. This is called dialogue management, and is handled by your Core model.

Core models learn from real conversational data in the form of training “stories”. A story is a real conversation between a user and an assistant. Lines with intents and entities reflect the user’s input and action names show what the assistant should do in response.

Below is an example of a simple conversation. The user says hello, and the assistant says hello back. This is how it looks as a story:

## story1
* greet
   - utter_greet
You can see the full details in Stories.

Lines that start with - are actions taken by the assistant. In this tutorial, all of our actions are messages sent back to the user, like utter_greet, but in general, an action can do anything, including calling an API and interacting with the outside world.

Run the command below to view the example stories inside the file data/stories.md:

cat data/stories.md

5. Define a Domain¶
The next thing we need to do is define a Domain. The domain defines the universe your assistant lives in: what user inputs it should expect to get, what actions it should be able to predict, how to respond, and what information to store. The domain for our assistant is saved in a file called domain.yml:

cat domain.yml
run
So what do the different parts mean?

intents	things you expect users to say
actions	things your assistant can do and say
templates	template strings for the things your assistant can say
How does this fit together? Rasa Core’s job is to choose the right action to execute at each step of the conversation. In this case, our actions simply send a message to the user. These simple utterance actions are the actions in the domain that start with utter_. The assistant will respond with a message based on a template from the templates section. See Custom Actions to build actions that do more than just send a message.

6. Train a Model
Anytime we add new NLU or Core data, or update the domain or configuration, we need to re-train a neural network on our example stories and NLU data. To do this, run the command below. This command will call the Rasa Core and NLU train functions and store the trained model into the models/ directory. The command will automatically only retrain the different model parts if something has changed in their data or configuration.

rasa train
​
echo "Finished training."
run
The rasa train command will look for both NLU and Core data and will train a combined model.

7. Talk to Your Assistant
Congratulations! 🚀 You just built an assistant powered entirely by machine learning.

The next step is to try it out! If you’re following this tutorial on your local machine, start talking to your assistant by running:

rasa shell

