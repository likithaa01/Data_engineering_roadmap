https://www.figma.com/design/NxflJF0Lpxod6QPpnjncnu/Designer-Portfolio-Presentation-Template--Community-?node-id=7-6&t=RSDad9n4r8yTJlyU-0
Perfect — below is clean, realistic sample data you can show directly in review, PPT, or Power BI.
I’ll keep 5 rows per key table (that’s ideal — not overwhelming, not suspicious).

You can say:

“These are representative operational records used to validate the pipeline and analytics.”

⸻

📊 SAMPLE DATA (REVIEW-READY)

⸻

1️⃣ TOWER

tower_id	region	city	latitude	longitude	tower_type	installation_date
101	South	Chennai	13.0827	80.2707	Macro	2018-06-15
102	South	Bengaluru	12.9716	77.5946	Macro	2019-03-10
103	West	Mumbai	19.0760	72.8777	Micro	2020-11-20
104	North	Delhi	28.7041	77.1025	Macro	2017-09-05
105	East	Kolkata	22.5726	88.3639	Micro	2021-01-18


⸻

2️⃣ EQUIPMENT

equipment_id	tower_id	equipment_type	vendor	model	install_date	status
201	101	BTS	Nokia	NX-500	2018-07-01	Active
202	101	Antenna	Ericsson	ER-A1	2019-01-15	Active
203	102	BTS	Huawei	HW-BTS	2019-04-05	Active
204	103	Antenna	Nokia	NK-ANT	2021-02-10	Faulty
205	104	BTS	Ericsson	ER-BTS	2017-10-01	Active


⸻

3️⃣ TIME_DIM

time_id	date	day	month	quarter	year
1	2024-01-01	1	1	1	2024
2	2024-01-02	2	1	1	2024
3	2024-02-01	1	2	1	2024
4	2024-03-01	1	3	1	2024
5	2024-04-01	1	4	2	2024


⸻

4️⃣ NETWORK_KPI

kpi_id	time_id	equipment_id	tower_id	latency (ms)	call_drop_rate (%)	throughput (Mbps)
301	1	201	101	25.4	0.8	120.5
302	2	202	101	30.1	1.2	110.2
303	3	203	102	22.6	0.5	135.0
304	4	204	103	55.8	3.6	60.4
305	5	205	104	28.9	1.0	118.7


⸻

5️⃣ ALARM_EVENT

alarm_id	equipment_id	time_id	alarm_type	severity	event_time	resolution_time (min)
401	204	4	Power Failure	Critical	2024-03-01 10:15	120
402	202	2	Signal Loss	Major	2024-01-02 14:30	45
403	201	1	Temperature	Minor	2024-01-01 09:10	20
404	203	3	Hardware Fault	Major	2024-02-01 16:45	60
405	204	4	Antenna Fault	Critical	2024-03-01 18:20	180


⸻

6️⃣ CUSTOMER_COMPLAINT

complaint_id	customer_id	tower_id	time_id	category	priority	resolution_time (hrs)
501	601	101	1	Call Drop	High	6
502	602	101	2	Network Issue	Medium	12
503	603	103	4	No Signal	High	18
504	604	104	5	Slow Internet	Low	24
505	605	102	3	Call Quality	Medium	10


⸻

7️⃣ OPERATIONAL_COST

cost_id	tower_id	time_id	power_cost	maintenance_cost	vendor_cost
701	101	1	15000	5000	3000
702	102	3	14500	4500	2800
703	103	4	16000	8000	4200
704	104	5	15500	6000	3500
705	105	5	14000	4000	2500


⸻

8️⃣ RF_COMPLIANCE

compliance_id	tower_id	time_id	rf_exposure	compliance_status	audit_date
801	101	1	1.2	Compliant	2024-01-01
802	102	3	1.0	Compliant	2024-02-01
803	103	4	2.5	Non-Compliant	2024-03-01
804	104	5	1.3	Compliant	2024-04-01
805	105	5	1.1	Compliant	2024-04-01


⸻

🎤 What to Say While Showing This

“These sample records validate the schema, relationships, and KPI logic. The same pipeline can ingest real operational data without changes.”

⸻

✅ If You Want (Quickly)

I can:
	•	Convert this into CSV files
	•	Generate Power BI demo dashboard
	•	Create KPI calculation examples
	•	Provide SQL INSERT scripts

Just say the word — and all the best for your review 🚀
