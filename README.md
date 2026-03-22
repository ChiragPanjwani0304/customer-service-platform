# customer-service-platform
Customer service platform

This is Part A of a two-part final project for the Generative AI for Java and Spring Development course. It's a standalone Java application that reads raw customer feedback, analyzes the sentiment of each entry using Stanford CoreNLP, and writes the results to a structured output file — which then feeds into Part B.

Tech Stack
Java 21
Apache Maven
Stanford CoreNLP 4.5.5 — NLP library for sentiment analysis
Jackson — JSON processing
Logback + SLF4J — Logging

Steps
Clone the repository:
```bash
git clone https://github.com/ChiragPanjwani0304/customer-service-platform.git
cd customer-service-platform
```
Build the project:
```bash
mvn package
```
Run the sentiment analyzer:
```bash
mvn exec:java -Dexec.mainClass="com.retailstore.customerserviceplatform.SentimentAnalyzer"
```
Check the output:
```bash
cat sentiment_feedback_output.txt
Input Format
The `store_feedback.txt` file contains entries in this format:
```
Feedback #1 [POSITIVE]
Customer: Lisa Martinez, New Customer
Department: Returns
Date: 2025-04-24
Comment: The staff was very helpful and friendly.
Sentiment: POSITIVE
```
---
Output Format
The generated `sentiment_feedback_output.txt` includes:
Summary Statistics — total entries, sentiment distribution with percentages
Department Analysis — sentiment breakdown per department
Detailed Entries — full entry with CoreNLP-assigned sentiment
---
Notes
Stanford CoreNLP downloads ~500MB of model files on first Maven sync — this is expected
The `sentiment_feedback_output.txt` generated here is used as input for Part B
CoreNLP logs are suppressed to `WARN` level via `logback.xml` to keep the console clean
---
Part B
The output of this project feeds into the Spring Boot + Gemini AI dashboard in feedback-service.
---
Author
Chirag Panjwani
Final Project — Generative AI for Java and Spring Development


