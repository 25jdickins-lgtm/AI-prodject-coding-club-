import os
from google import genai

# 1. Initialize the client (looks for GEMINI_API_KEY environment variable)
client = genai.Client()

print(" AI Bot Initialized! Type 'quit' to exit.")

while True:
    user_input = input("\nYou: ")
    if user_input.lower() == 'quit':
        break
        
    # 2. Generate the content using a fast, lightweight model
    response = client.models.generate_content(
        model='gemini-2.5-flash',
        contents=user_input,
    )
    
    # 3. Print the text response
    print(f"\nAI: {response.text}")
