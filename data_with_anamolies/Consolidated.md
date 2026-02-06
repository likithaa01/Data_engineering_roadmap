import json
import random
from datetime import datetime, timedelta

BASE_DIR = "unstructured_data"

# -------------------------
# Sample content pools
# -------------------------
equipment_logs = [
    "RF signal drop detected",
    "Automatic retry initiated",
    "Hardware temperature high",
    "Connection timeout occurred",
    "Power fluctuation observed"
]

alarm_descriptions = [
    "Critical alarm due to overheating",
    "Major alarm: signal loss",
    "Minor alarm: voltage variation",
    "Critical alarm: equipment failure"
]

site_visit_reports = [
    "Tower location inaccessible due to rain",
    "Antenna alignment required",
    "Power backup below threshold",
    "Site inspection completed successfully"
]

maintenance_notes = [
    "Temporary fix applied",
    "Cable replacement required",
    "Battery backup replaced",
    "Preventive maintenance completed"
]

complaint_notes = [
    "Frequent call drops reported",
    "Internet speed very slow",
    "No signal inside building",
    "Network unavailable during evening"
]

call_transcripts = [
    "Agent: Please describe the issue.\nCustomer: Calls are dropping frequently.",
    "Agent: When did the issue start?\nCustomer: Since yesterday evening.",
    "Agent: Which location?\nCustomer: Near Whitefield."
]

rf_status = ["Compliant", "Marginal", "Non-Compliant"]

# -------------------------
# Helper to write 100 text records
# -------------------------
def write_text_file(filename, content_list):
    with open(f"{BASE_DIR}/{filename}", "w") as f:
        for i in range(1, 101):
            timestamp = (datetime.now() - timedelta(minutes=i)).isoformat()
            record = f"[{i}] {timestamp} - {random.choice(content_list)}\n"
            f.write(record)

# -------------------------
# Generate TEXT files
# -------------------------
write_text_file("equipment_logs.txt", equipment_logs)
write_text_file("alarm_descriptions.txt", alarm_descriptions)
write_text_file("site_visit_reports.txt", site_visit_reports)
write_text_file("maintenance_notes.txt", maintenance_notes)
write_text_file("call_transcripts.txt", call_transcripts)
write_text_file("complaint_notes.txt", complaint_notes)

# -------------------------
# Generate RF Audit JSON
# -------------------------
rf_audit_records = []

for i in range(1, 101):
    rf_audit_records.append({
        "audit_id": f"RF_{i}",
        "tower_id": f"TWR_{random.randint(1000,1100)}",
        "audit_date": (datetime.now() - timedelta(days=i)).date().isoformat(),
        "rf_exposure": round(random.uniform(0.5, 2.5), 2),
        "compliance_status": random.choice(rf_status),
        "remarks": "Measured RF levels within assessed range"
    })

with open(f"{BASE_DIR}/rf_audit.json", "w") as f:
    json.dump(rf_audit_records, f, indent=2)

print("✅ All unstructured data files created with 100 records each.")
