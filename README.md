# Chat-GPT-Data-Analyst

**Installation**
First you will need the pypeline library that allows us to run python queries, which is what we do when we use OpenAI. You can download it here: https://github.com/t-wolfeadam/AnyLogic-Pypeline

Second, download and include this library in your AnyLogic palette. You can get more instructions here: https://anylogic.help/advanced/libraries/managing-libraries.html#add

Make sure you have Python installed in your machine, and install the following libraries in your python environment: python-dotenv & openai. 

**Configuration**  
**Text Font Section**
1.	You can change the text font of the title and the chat. Feel free to experiment to see what’s best for you.

**General Configuration**  
1.	Data time unit is what chat gpt will use as time units for the answers. You will have to be consistent with this time units when you give data to the chat as we will discuss later.
2.	In Python path parameter you need to write the path where your python executable is in your computer. If you use windows, it should look something like this: “C:\\Users\\myName\\Anaconda3\\python.exe”. 
3.	The Api key is the unique identifier for each OpenAI user. You can find it in https://platform.openai.com/api-keys. You will need to log in or create an account and then once inside, click on “Create new secret key” and save that secret key in a note. (after you close the window, you will not be able to see this secret key again). Paste that key in the Api key parameter.
4.	Now to configure the Assistant key parameter: Go to https://platform.openai.com/assistants and click on “+ Create”. Write a name for your assistant. Write the instructions for your assistant, here you can write how do you want the chat AI to behave for all your interactions and to give some context on what the model is about. For example: “Answer questions in a maximum of 80 words as an expert in epidemiology and an expert in data science and statistics. Only provide conclusions and answers related to data. The data has this format: NameOfStat:{{Time:Value}}”. The format at the end is how we communicate data to openAI and it is useful to add it to get better results. Feel free to experiment with the assistant text to get the best results from your model giving context and behavior. This is one of the important things you need to do trial-error until you get as close to what you want. Not always easy. Now select your Model, by default you can use one of the gpt-3.5-turbo models or if you would like a better performance (but more expensive too) you can use one of the gpt-4 models. In order to see the gpt-4 models available, you have to setup a payment method, otherwise gpt-4 will not be visible. (You can find the cost for each model here https://openai.com/pricing). Hard to understand, so be sure you monitor your expenses. You can add money to your openAI platform here: https://platform.openai.com/account/billing/overview. Now you can copy the assistant key (which is under the assistant name you chose) and paste it in Assistant key parameter of the chat agent.
5.	Response update time (seconds): is how often the API checks if the response is ready. You can leave that as it is.
  
IMPORTANT: if you don’t have credit in your open AI platform, you will NOT get any responses from the chat. If you are using it for the first time, you might get initial credits for GPT-3.5, but not for 4.0 or superior.

**Chat presentation**  
You can also modify the chat presentation with the following parameters. Feel free to experiment to find what works best for you.
1.	Chat width: the width of the chat in pixels.
2.	Space between text: space in pixels between each line of text.
3.	Number of chat lines to show: maximum number of lines displayed in the chat.
4.	TextBox height: the height of the textbox where the prompt is written.
5.	Button height: the height of the buttons like reset and run response.
6.	Max characters per line: maximum number of characters per line.

**How to add data to the AI agent**  
once you have the chat agent in your model, you can use the following methods:
1. addStat(String nameOfData, Double time, String dataPoint);
The method addStat takes 3 arguments:  
•	The name of the data  
•	The time in which this data was collected. Chat GPT will assume the time units will be the ones you defined in the configuration.  
•	The value of this data must be converted to a String. We do that because not all data is necessarily a number.  

2. If you want to reset your data, you can use the function resetStats().
