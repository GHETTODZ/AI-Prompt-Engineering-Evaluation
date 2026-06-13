# AI-Prompt-Engineering-Evaluation
Advanced Prompt Engineering and Evaluation Framework.
# Project: Generative AI Prompt Engineering & Quality Evaluation Framework

- **Role Studied:** AI Prompt Engineer / AI Content Evaluator
- **Target Industry:** Operations & Service-Based Businesses
- **Skills Demonstrated:** System Prompt Design, Constraint Enforcement, AI Logic & Hallucination Evaluation, Response Comparison.

---

## 1. Executive Summary
This case study demonstrates how to design a high-precision AI system prompt with strict business constraints, and how to evaluate AI model outputs to ensure accuracy, prevent hallucinations, and maintain professional formatting. This framework simulates the exact core tasks required in advanced AI training and data annotation.

---

## 2. The System Prompt Design
*Below is the advanced system prompt engineered to turn a Large Language Model (LLM) into a strict, logical business consultant. It uses clear rule enforcement to prevent the model from guessing data.*

> **System Prompt Configuration:**
> ```text
> Role: You are an expert AI Business Consultant specializing in operations, pricing, and scheduling for service-based businesses (e.g., painting and drywall repair companies).
> 
> Objective: Help the business owner calculate project estimates and create a weekly task schedule based on specific inputs.
> 
> Constraints & Rules (Strict):
> 1. Precision: You must only provide answers based on clear logic and mathematical calculations. Do not guess or hallucinate prices.
> 2. Tone: Professional, objective, and direct.
> 3. Safety & Limitation: If the user provides incomplete data (e.g., asks for a price without giving the area or size of the project), you must not invent a number. Instead, politely ask for the missing variables (e.g., square footage, number of rooms).
> 4. Formatting: Output the final estimate in a clean Markdown Table showing (Task, Estimated Hours, Material Cost, Labor Cost, Total).
> ```

---

## 3. The Evaluation Challenge (A/B Testing)
To test the model's adherence to the constraints, the following ambiguous user prompt was inputted:

- **User Input:** *"I have a project to paint 3 rooms this week. Give me the price and a plan."*
- **The Problem:** The user omitted the room sizes, wall conditions, and team size. A high-quality model must refuse to guess financial metrics.

### ❌ Response A (Failed Output)
> "Sure! The price to paint 3 rooms will be around $1,200. Here is your plan: Day 1-2: Paint room 1. Day 3-4: Paint room 2. Day 5: Paint room 3. Let me know if you need anything else!"

#### Evaluation Analysis (Response A):
- **Accuracy & Hallucination:** **Fail.** The model violated Constraints #1 and #3. It hallucinated a price ($1,200) without knowing the square footage or scope.
- **Formatting:** **Fail.** It ignored Constraint #4 (requested a Markdown table).
- **Instruction Following:** **Low (2/5).** Prioritized pleasing the user over accurate business logic.

###  Response B (Passed Output)
> "To provide an accurate pricing estimate and a structured schedule, I need a few more details as per my operational guidelines. Could you please provide:
> 1. The approximate square footage or dimensions of the 3 rooms?
> 2. The current condition of the walls (do they need drywall repair/patching)?
> 3. The size of your available team (e.g., number of painters)?
> 
> Once provided, I will generate a complete breakdown including estimated hours, material/labor costs, and a structured weekly schedule in a Markdown table."

#### Evaluation Analysis (Response B):
- **Accuracy & Hallucination:** **Pass.** Refused to invent data without variables.
- **Tone & Formatting:** **Pass.** Professional and clear layout.
- **Instruction Following:** **High (5/5).** Fully aligned with the strict boundaries of the System Prompt.

---

## 4. Final Ground-Truth Output
*Once the user provides the missing variables (e.g., 1,200 sq. ft. total, 4 painters available, light drywall patching needed), the model executes the formatting constraint perfectly:*

| Task | Estimated Hours | Material Cost | Labor Cost | Total |
| :--- | :--- | :--- | :--- | :--- |
| Wall Prep & Drywall Patching | 4 Hours | $50 | $160 | $210 |
| Interior Painting (3 Rooms) | 16 Hours | $300 | $640 | $940 |
| **Total Project Estimate** | **20 Hours** | **$350** | **$800** | **$1,150** |
