Nikath
For our chatbot to behave like AI we got an API key which was created from aistudio.google.com and created a free API gemini key this allowed the chatbot to talk like AI 
For the interface we created a html file for the design of the interface like the buttons, chat bubbles, background and this file was capable of running on any browser. 
The first key had quota issues so we got another key for better ai functioning from groq API the model changed to LLama 3.3 70B instead of Gemini 


Noor
Then we further deployed the chatbot on the Github Pages containing all the public links so that it becomes accessible to everyone having the link online.
This was then enhanced with the image that was uploaded so that the users can submit all the lab reports, which further analyses using AI using the Llama 4 Scout Vision model.
Further it was integrated with a RAG Pipeline that helps search using the medical knowledge before giving the responses which will be context based.


Rohini
Guardrails are implemented at two levels: input guardrails block unsafe or invalid queries.
Output guardrails ensure the responses generated are reliable, appropriate, and safe to use.
So basically we build a medical chatbot that anyone can open and ask health questions. 
In this groq runs the AI,GitHub stores and host the code and HTML/JS makes everything look and work nicely 
In the browser and we used RAG the basis of medical information and with the help of this it finds relevant information to answer


Stack
In this project, we used HTML for the frontend interface.
The backend includes AI model integration, RAG pipeline, and guardrails logic.
The system is deployed as a web-based application for user access.


The GenAI part is responsible for generating intelligent responses.
It includes a language model that understands and answers queries.
RAG is used to retrieve real medical data before generating answers.
Guardrails ensure the responses are safe, accurate, and not misleading.
