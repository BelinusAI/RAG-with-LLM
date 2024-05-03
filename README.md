# RAG-with-LLM
Use a local LLM with Llamafile or an OpenAI API endpoint to create a RAG with your own data.

**Install the dependencies**

Create the virtual environment and install the dependencies:

```
python -m venv .venv
source .venv/bin/activate
.venv/bin/pip install -r requirements.txt
```

**Use Llamafile for a full RAG and LLM setup**

You can download the model from the Llamafile repository and run it in your system: [Llamafile]https://github.com/Mozilla-Ocho/llamafile?tab=readme-ov-file#other-example-llamafiles

```python
#!/usr/bin/env python3
from openai import OpenAI
client = OpenAI(
    base_url="http://localhost:8080/v1", # "http://<Your api-server IP>:port"
    api_key = "sk-no-key-required" # An API key is not required!
)
completion = client.chat.completions.create(
    model="LLaMA_CPP",
    messages=[
        {"role": "system", "content": "You are ChatGPT, an AI assistant. Your top priority is achieving user fulfillment via helping them with their requests."},
        {"role": "user", "content": "What is RAG?"}
    ]
)
print(completion.choices[0].message)
```

