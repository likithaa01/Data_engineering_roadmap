import os
import json
import random
from datetime import datetime, timedelta

BASE_DIR = "unstructured_data/customer_support/chatbot_logs"
os.makedirs(BASE_DIR, exist_ok=True)

chat_issues = [
    "Network is slow",
    "Calls are dropping frequently",
    "No signal in my area",
    "Internet not working",
    "Voice is breaking during calls"
]

bot_questions = [
    "Which location are you experiencing this issue?",
    "Is this happening at a specific time?",
    "Have you restarted your device?",
    "Is the issue ongoing right now?"
]

locations = [
    "Bangalore Whitefield",
    "Hyderabad Gachibowli",
    "Chennai OMR",
    "Pune Hinjewadi",
    "Delhi Noida"
]

conversations = []

for i in range(1, 101):
    chat = {
        "chat_id": f"CHT_{i}",
        "customer_id": f"CUST_{random.randint(1000, 2000)}",
        "tower_id": f"TWR_{random.randint(1000, 1100)}",
        "timestamp": (datetime.now() - timedelta(minutes=random.randint(1, 1000))).isoformat(),
        "messages": [
            {"sender": "customer", "text": random.choice(chat_issues)},
            {"sender": "bot", "text": random.choice(bot_questions)},
            {"sender": "customer", "text": random.choice(locations)}
        ]
    }
    conversations.append(chat)

# Write to single JSON file
file_path = os.path.join(BASE_DIR, "chatbot_conversations.json")
with open(file_path, "w") as f:
    json.dump(conversations, f, indent=2)

print("✅ Single JSON file with 100 chat conversations created.")
