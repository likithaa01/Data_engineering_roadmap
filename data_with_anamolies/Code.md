import os
import json
import random
from datetime import datetime, timedelta

BASE_DIR = "unstructured_data"

def create_dir(path):
    os.makedirs(path, exist_ok=True)

# ------------------------------
# 1. Customer Support Data
# ------------------------------
complaint_texts = [
    "Frequent call drops observed near tower.",
    "Network speed is slow during peak hours.",
    "Signal fluctuates between weak and no service.",
    "Unable to make outgoing calls.",
    "Internet connectivity unstable."
]

call_transcript_template = [
    "Agent: Please describe the issue.",
    "Customer: Calls keep disconnecting.",
    "Agent: Since when?",
    "Customer: From yesterday evening."
]

chatbot_messages = [
    "Network is slow",
    "Calls are dropping",
    "No signal in my area",
    "Internet not working"
]

# ------------------------------
# 2. Network Logs
# ------------------------------
log_levels = ["INFO", "WARN", "ERROR"]
alarm_messages = [
    "Overheating detected",
    "Power fluctuation detected",
    "Signal loss observed",
    "Hardware failure suspected"
]

# ------------------------------
# 3. Field Engineer Notes
# ------------------------------
maintenance_notes = [
    "Antenna cable damaged",
    "Battery backup weak",
    "Water seepage observed",
    "Temporary fix applied"
]

# ------------------------------
# 4. Compliance Notes
# ------------------------------
rf_results = [
    "Within permissible limits",
    "Marginally high but acceptable",
    "Fully compliant"
]

# ------------------------------
# Create folders
# ------------------------------
paths = [
    "customer_support/complaint_notes",
    "customer_support/call_transcripts",
    "customer_support/chatbot_logs",
    "network_logs/equipment_logs",
    "network_logs/alarm_descriptions",
    "field_engineer/maintenance_notes",
    "field_engineer/site_visit_reports",
    "compliance/rf_audit_summaries",
    "compliance/rf_inspection_images"
]

for p in paths:
    create_dir(os.path.join(BASE_DIR, p))

# ------------------------------
# Generate 100 records
# ------------------------------
for i in range(1, 101):

    # Complaint Notes
    with open(f"{BASE_DIR}/customer_support/complaint_notes/complaint_{i}.txt", "w") as f:
        f.write(random.choice(complaint_texts))

    # Call Transcripts
    with open(f"{BASE_DIR}/customer_support/call_transcripts/call_{i}.txt", "w") as f:
        f.write("\n".join(call_transcript_template))

    # Chatbot Logs (JSON)
    chatbot_data = {
        "chat_id": f"CHT_{i}",
        "customer_id": f"CUST_{random.randint(1000, 2000)}",
        "timestamp": str(datetime.now()),
        "message": random.choice(chatbot_messages)
    }
    with open(f"{BASE_DIR}/customer_support/chatbot_logs/chat_{i}.json", "w") as f:
        json.dump(chatbot_data, f, indent=2)

    # Equipment Logs
    log_time = datetime.now() - timedelta(minutes=random.randint(1, 500))
    log_entry = f"{log_time} {random.choice(log_levels)} {random.choice(alarm_messages)}"
    with open(f"{BASE_DIR}/network_logs/equipment_logs/equipment_log_{i}.log", "w") as f:
        f.write(log_entry)

    # Alarm Description
    with open(f"{BASE_DIR}/network_logs/alarm_descriptions/alarm_{i}.txt", "w") as f:
        f.write(random.choice(alarm_messages))

    # Maintenance Notes
    with open(f"{BASE_DIR}/field_engineer/maintenance_notes/maintenance_{i}.txt", "w") as f:
        f.write(random.choice(maintenance_notes))

    # Site Visit Reports
    with open(f"{BASE_DIR}/field_engineer/site_visit_reports/site_visit_{i}.txt", "w") as f:
        f.write("Site inspected. Issue identified. Resolution planned.")

    # RF Audit Summary
    with open(f"{BASE_DIR}/compliance/rf_audit_summaries/rf_audit_{i}.txt", "w") as f:
        f.write(random.choice(rf_results))

    # RF Inspection Image Placeholder
    with open(f"{BASE_DIR}/compliance/rf_inspection_images/rf_image_{i}.jpg", "w") as f:
        f.write("Binary image placeholder")

print("✅ 100 unstructured data files generated successfully.")
