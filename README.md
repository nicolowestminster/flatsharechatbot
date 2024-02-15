# Ai Based Pre-Qualification & Administration: Real Estate Management Chatbots
Real Estate Flatshare Chatbot
Student: Nicolo D’Avino (w18630585)

Supervisor: Dr Malarvizhi Kaniappan Chinnathai

This report is submitted in partial fulfillment of the requirements for the 
BSc (Hons) Data Science and Analytics 
at the University of Westminster.


School of Computer Science & Engineering
University of Westminster

## Table of contents

1.	Problem Understanding and Scoping (page 3)
2.	Aim and Objectives (page 4)
3.	Methodology (page 5)
3.1. Data Collection and Preparation (page 6)
3.1.1. Data Collection (page 6)
3.1.2. Results (page 7)
4.	Project Management and Planning (page 9)
5.	Prototype (page 11)
6.	Annotated Bibliography (page 11)
7.	References (page 11)
8.	Appendix I

## Problem Understanding and scoping
The project targets a challenge in the real estate sector, focusing primarily on the flatshare market and the tasks that estate agents that work in this field have to complete on a daily basis.

In the flatshare real estate market, agents communicate primarily using messaging platform like WhatsApp, which is where all of the communications take place. The main issue is the time-consuming and inefficient process of pre-qualifying applicants, which involves an introductory conversation and a light financial assessment of the accommodation candidate. The complexity of this problem revolves around the high volume of enquiries received every day and the need for accuracy and unbiased checks of each applicant suitability
(According to data from SpareRoom, there is a sharp increase in demand of shared accomodations, the ratio of available rooms and prospective tenants is 1:5 “SpareRoom (no date) Rental market shows signs of improvement. https://m.spareroom.co.uk/statistics/rental-market-shows-signs-of-improvement.”)
Furthermore, the problem directly impacts the efficiency of the estate agents working in this sector and the satisfaction of the applicants. Based on my own experience in industry, working in the largest HMO (House in Multiple Occupation)  accommodation provider in England for the past 5 years (I started my journey in the HMO space as a letting agent and then moving to business development management), I can confirm that the existing manual conversational process is not only time-consuming and labour-intensive, but is also prone to errors, most of the conversations with applicants happen after working hours and can continue until late night as most of the agents working in the flatshare real estate market are paid mostly in commissions and have a lower basic salary, making them feel the need of pre-qualifying candidates continuously. This can lead to potential losses for the agency and frustration of the applicants if the assessment of the customer is not conducted without bias or within a specific timeframe because agents might favour certain applicants based on perceived likelihood of a successful deal closure, which will lead to unfair treatment of potential tenants and resulting in bad reviews and an overall negative satisfaction due to a perceived lack of fairness and inconsistencies in information provided by the agents. In a research conducted in 1994, has been compared the accuracy of a salesperson in different industries and it founds that salespeople are generally inaccurate and emphasises the need to improve their perception and accuracy. The findings suggest that an inaccurate or biased assessment could lead to decision that are not optimal, directly impacting the agency’s performance and customer’s satisfaction. [3]
The above problem description underscores the need for a more systematic approach, automating this process with a chatbot that conversates directly with the applicants can significantly enhance efficiency, accuracy and user experience [5], and it also allows the agent on focusing on the second part of the customer’s journey such as conducting viewings and focusing on additional administrative tasks.

## Aim and Objectives
The purpose of the project is the development of an AI-based chatbot agent that can enhance and reinvent the pre-qualification process for flatshare real estate agents. The chatbot is intended to automate and improve the initial interaction with potential tenants in order to reduce the time and effort required by the agents in building rapport and deliver on manual conversations. The primary aim is to enhance efficiency, accuracy and fairness in the customer’s journey, ultimately leading to improved agent productivity and overall satisfaction for both agents and applicants.

To achieve this the project will have several specific steps:
1.	To create a chatbot and integrate a large language models (GPT 3.5 Turbo, which is a great model with 175B parameters and has been optimised for Chat [4])
2.	Creation of a synthetic dataset with examples of Q&A
3.	Fine-tune the chatbot to enhance its ability to handle real-world scenarios with the created synthetic data that simulates the various applicant interactions and possible queries
4.	Automating the pre-qualification process and set the chatbot to conduct the initial assessment by asking relevant questions to determine the suitability for a room
5.	Integration into a messaging platform such as a website or WhatsApp
6.	Testing and feedback

## Methodology
1.	Literature Review and Market Analysis:
Conducted a literature review of what is already available today as a tool that helps agents solve the pre-qualification process specifically in flatshares. With 5 years experience in the flatshare industry I used the knowledge accrued in this field to elaborate the challenges and solutions.
2.	Design and Development of AI chatbot:
Creation of the basic chatbot that works using a LLM connected to Python (this will be a basic functionality and an initial setup where the chatbot will just be able to conversate with the user by leveraging the LLM data).
3.	Fine-tuning the LLM with synthetic data that simulates real-world scenarios. The generation of the synthetic data will happen first in Excel with a spreadsheet created with examples of Questions and Answers that an applicant can elaborate during the pre-qualification process, then the spredsheet is expanded using ChatGPT to expand the examples without going out of context.
4.	The integration of the chatbot will happen connecting python to the WhatsApp API thanks to the Meta Developer Tools, that allow the connection of the WhatsApp API (currently owned by Meta) and the project that is being built. Every time a user will send a WhatsApp message to a designated phone number related to the chatbot that has been created, the active server will trigger the fine-tuned LLM to start the pre-qualification process.
5.	To conduct multiple testing and gather some feedback to refine the chatbot. The tests will be manually conducted and then redefine the parameters of the LLM to make the chatbot only answers to relevant questions as the challenges will revolve around the LLM not going out of context.

## Data Collection, preparation
For the Ai Based Flatshare Agent Chatbot, the data that has been used has been mainly created by personal experience and an adaptation of the various conversations that take place when pre-qualifying someone that wants to rent a room. In most of the cases, the conversations are methodical and have the same pattern. The pre-qualification phase doesn’t require knowing a lot about the applicant, therefore the data can be easily replicable and expanded by using a tool such as ChatGPT.
### 3.1.1 Data Collection:
1.	Synthetic Dataset Creation: As explained above, with data taken from personal experiences, a synthetic dataset was created, which derives from a blend of real-world scenarios of conversations that happens almost all the time and in the same way with different applicants, and the expansion of the examples using ChatGPT. Most of the time applicants approach agents to check if a room is still available and to organise a viewing. In order to satisfy their request of viewing the room, a check needs to be completed and common questions that the an agent needs to ask in the initial phase are: Is the room just for yourself? Are you a student or a professional? What is your income? Would you be able to add a guarantor?
2.	The data was initially created added in an Excel table. The format chosen was structured to align with the requirements of OpenAi’s fine-tuning accepted format, ensuring compatibility between the data synthetically created and the way the model reads the data that is used for the training phase of the model.
3.	Example 1 data added by myself: {"messages": [{"role": "system", "content": "Nicolo is a Flatshare estate agent that is helpful and will do a quick pre-qualification check and collect some information from the client."}, {"role": "user", "content": "Hi, I'm sending you the message on WhatsApp as you requested me to message you here"}, {"role": "assistant", "content": "Hi, thanks for messaging me on WhatsApp, May I please ask you what is the cost of the room that you messaged me for?"}]}

    Example 2 data added by myself: {"messages": [{"role": "system", "content": "Nicolo is a Flatshare estate agent that is helpful and will do a quick pre-qualification check and collect some information from the client."}, {"role": "user", "content": "The cost of the room is 900 per month"}, {"role": "assistant", "content": "Ok thanks! Is the room just for yourself or you will be moving together with another person?"}]}
4. Expansion with ChatGPT: To make the dataset larger as recommended by OpenAi (according to their fine tuning guide, there is the need of 50-100 examples to fine tune a model), ChatGPT was used and the application helped in creating more examples of potential conversations. This process involved asking ChatGPT to create 50 new examples based on the initial template provided, the aim was to get as many examples as possible and with a higher variety of potential words order used in the interactions between the agent and the applicant
5.	Conversion to JSON Lines format: The CSV file was transformed into a JSON Lines (.jsonl) file. This format is required for the training data in the OpenAi’s environment, especially for fine-tuning GPT 3.5 Turbo. The conversion to this file format is crucial for the compatibility and efficiency in handling datasets for machine learning purposes. The JSON Lines format ensures that the structuring of the data is simple and readable and is effectively in nature closer to a dialogue, which is essential for training Ai models like GPT 3.5 Turbo.

### Results:
1. The results of the fine tuning process using the synthetic dataset were promising and successfully completed. To take in consideration for the evaluation we need to take a look at the cost for fine tuning the model ($0.13 in the final fine-tuned model) and the training loss. There is absence of error in the synthetic dataset provided for fine-tuning which confirms the correct format of the data in the JSON file (the distribution of messages in every example is always 3.0, which means that the data has always 3 sets of sentences to elaborate), and the token limit of 4096 token is respected, which ensures that no data will be truncated and it is important to maintain data integrity in the process.
2. The fine-tuning job was successfully created and the fine-tuning job was initiated. The process had 240 steps to complete and at each step there is a training loss value, which explains how well the model is performing (a lower training loss indicates better performance). The improving value of the training loss indicates that the model is adjusting and learning from the data, for instance at the beginning it is possible to see higher loss and a gradual decline in loss through the end of the process. 
The fine-tuned model is expected to perform better in the agent specific use case compared to a general purpose model in handling queries that are related to the flatshare market, and it shows that a fine-tuning process can be adapted for different agents and the relative standards they need to pre-qualify applicants and can be adapted in different industries as well as the one elaborated in this project.

### Tools and Techniques:
1.	Excel for the initial data composition and organisation of the agent/applicant conversations
2.	ChatGPT for the synthetic dataset expansion
3.	Google Colab as an environment to use Python for the conversion of the CSV file into a JSON Lines file and for Fine-Tuning GPT 3.5 Turbo.

## Project Management and Planning
The development of the chatbot project needs a structured approach to project management and planning. Initially, the project embarked on the ambitious task of developing fine-tuning using an open source LLM (Mistral). This phase involved comprehensive research into the available models and capabilities, and Mistral 7B (with 7 billion parameter, is an open source large language model that performs greatly even in comparison with larger models that include Llama 2 13B created by Meta [2]) looked the most convenient for weight and ability to produce outputs that perform well. I developed the chatbot making Mistral running on a personal device. The output was generating 12 token per second on a laptop with 16Gb of ram, running without GPU offload (sufficient to produce a timely output). Then with the use of a local internet server, Mistral and Python were connected and this seemed to be the best option available in order to run the chatbot on a local machine. The realisation that, if choosing to keep using Mistral for fine tuning and for the utilisation in the chatbot would have take longer than expected, GPT 3.5 from OpenAi was employed to continue the project.
The fine-tuning phase didn’t take long, and it approximately took one day to completion, after creating the first rows of examples in Excel and providing the information to ChatGPT, the list of 80 examples was produced and transformed into the correct file format (.jsonl) to use as training synthetic data to provide to use for the fine-tuning GPT 3.5 Turbo. The fine-tuning it’s a relatively short process, with 80 JSON objects, it takes around 20 minutes for the fine-tuning to complete (I tried fine-tuning 6 times before reaching the desired level of produced output). The final output produces a highly acceptable level of response quality, the chatbot is able to get the context and answers as an agent for the majority of the times.
The project has potential risks: one risk if the potential of the fine-tuned model to deviate from the desired output and going out of the conversation. To mitigate this a more detailed synthetic dataset will be created. Another risk is the model’s ability to perform mathematical calculations when requested to perform the ‘applicant’s minimum affordability’ (Monthly room cost * 30 <= Applicant’s yearly salary). A way to implement this is to create a structured output and give better instructions to the model using ‘Function-calling’ in order to get better formatted responses and a more consistent output.
The WhatsApp integration has not yet started and it will take place after the final adjustment to the output structure of the chabot. Using WhatsApp as a chatbot, according to a survey [1] conducted by a group of students at the IMS Engineering College in Ghaziabad (India) has 3 potential benefits, first one with 64% of positive responses is having a 24h service, second one is having quick responses (55% of positive answers) and third one is answering to simple generic questions (55% positive response).
The meetings with my supervisor helped in getting a better idea on how to structure the project, the guidance provided a dive into the steps needed to complete the chatbot in a timely manner. The supervisor indicated that the best approach would’ve been finding existing project and compare it with this one. The recommendation was to create an Excel table with a comparison of existing projects, their pros and cons, showing what could’ve been improved. 
As of today, after an extensive research of academic papers, no other projects have been built as a chatbot that replicates an estate agent that pre-qualifies applicants. 

## Annotated Bibliography
1.	OpenAi Platform – Fine Tuning Guide ( https://platform.openai.com/docs/guides/fine-tuning/preparing-your-dataset ):
This guide provides a an overview of the steps needed in fine-tuning models using OpenAi’s API. It explains the process of preparing and uploading the training data, training the fine tuned model and evaluating the results. The guide is essential for understanding the aspects of the model training, especially for projects that focus on personalising a model for a specific use case.
2.	OpenAi Cookbook – Chat Fine-Tuning Data Preparation - Michael Wu, Simón Fishman Aug 22, 2023
(https://cookbook.openai.com/examples/chat_finetuning_data_prep): This resource provides a guide on preparing and analysing the data for fine-tuning a model. Includes the essential format for a successful data preparation, token count and cost estimation for fine tuning GPT 3.5 Turbo. This guide is helpful mostly for ensuring that data integrity aligns with the fine-tuning process.
3.	Quick Start Guide to Large Language Models: Strategies and Best Practices (Book): The book is a comprehensive guide on Large Language Model and give a clear explanation on many aspects of the LLM world. Particularly in Chapter 4 where it shows how Transfer Learning can leverage pre-trained models to implement specific tasks, actions and sentence formulation to adapt to different topics, company’s legal structures or guidelines.
Ozdemir, S., 2023. Quick Start Guide to Large Language Models: Strategies and Best Practices for Using ChatGPT and Other LLMs. Addison-Wesley Professional. (https://books.google.co.uk/books?hl=en&lr=&id=aDvVEAAAQBAJ&oi=fnd&pg=PT18&dq=fine+tuning+llm+chatbot&ots=9hX5z3GWVH&sig=OnhyEf2h-ig85aDqXKipuq9Xa6s&redir_esc=y#v=onepage&q=fine%20tuning%20llm%20chatbot&f=false) 

## References
[1] Jindal, G., Upadhyay, D. and Jha, A., 2020. Whatsapp chatbot. EasyChair Preprint, 3641, p.40.
[2] Jiang, A.Q., Sablayrolles, A., Mensch, A., Bamford, C., Chaplot, D.S., Casas, D.D.L., Bressand, F., Lengyel, G., Lample, G., Saulnier, L. and Lavaud, L.R., 2023. Mistral 7B. arXiv preprint arXiv:2310.06825.
[3] (Sharma, A. and Lambert, D.M., 1994. How accurate are salespersons' perceptions of their customers?. Industrial Marketing Management, 23(4), pp.357-365.)
[4] Ye, J., Chen, X., Xu, N., Zu, C., Shao, Z., Liu, S., Cui, Y., Zhou, Z., Gong, C., Shen, Y. and Zhou, J., 2023. A comprehensive capability analysis of gpt-3 and gpt-3.5 series models. arXiv preprint arXiv:2303.10420.
[5] Pandya, K. and Holia, M., 2023. Automating Customer Service using LangChain: Building custom open-source GPT Chatbot for organizations. arXiv preprint arXiv:2310.05421.
