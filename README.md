## Design and Implementation of LangChain Expression Language (LCEL) Expressions

### AIM:
To design and implement a LangChain Expression Language (LCEL) expression that utilizes at least two prompt parameters and three key components (prompt, model, and output parser), and to evaluate its functionality by analyzing relevant examples of its application in real-world scenarios.

### PROBLEM STATEMENT:
### DESIGN STEPS:

#### STEP 1: Create a prompt template with two parameters, sport and country.

#### STEP 2: Connect the Prompt, Chat Model, and Output Parser using the LCEL pipe (|) operator.

#### STEP 3: Execute the chain using invoke() with the inputs cricket and India to generate the output.

### PROGRAM:
````
Name: SAAINATH B
Reg no: 212225240127
import os
import openai
​
from dotenv import load_dotenv, find_dotenv
_ = load_dotenv(find_dotenv()) # read local .env file
openai.api_key = os.environ['OPENAI_API_KEY']

from langchain.prompts import ChatPromptTemplate
from langchain.chat_models import ChatOpenAI
from langchain.schema.output_parser import StrOutputParser
gpt-4.1-mini
prompt = ChatPromptTemplate.from_template(
    "tell me a famous player in {sport} and in {country}"
)
model = ChatOpenAI(model="gpt-4.1-mini")
output_parser = StrOutputParser()

chain = prompt | model | output_parser
chain.invoke({"sport": "criket"},{"country": "india"})
chain.invoke({"sport": "cricket", "country": "India"})
````

### OUTPUT:
<img width="1182" height="78" alt="image" src="https://github.com/user-attachments/assets/637bc6f4-1e10-4d61-aa94-d5b4359c9807" />


### RESULT:
RESULT:

Thus, the LCEL expression was successfully designed and implemented using two prompt parameters (sport and country) and three key components (Prompt, Model, and Output Parser). The chain was executed successfully to generate the response about a famous cricket player from India.
