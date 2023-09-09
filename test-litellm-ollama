from litellm import completion
import os
## set ENV variables
use_ollama=True
# use_ollama=False
os.environ["OPENAI_API_KEY"] = "fill key here and set use_ollama to false if you want to compare with open gpt3.5-turbo"

messages = [{ "content": "repeat 'hi'","role": "user"}]
ollama_api_base = 'http://localhost:11434'
ollama_model_name = 'codellama'

if use_ollama:
    response = completion(
        model=ollama_model_name,
        api_base=ollama_api_base,
        custom_llm_provider="ollama",
        messages=messages,
        stream=True
    )
else:
    response = completion(model="gpt-3.5-turbo", messages=messages, stream=True)

for chunk in response:
    print(chunk['choices'][0]['delta'])
