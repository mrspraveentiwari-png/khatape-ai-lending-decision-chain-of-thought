# FinBuddy: Making a Bank's AI Assistant Follow the Rules with a System Prompt

**A FinTech case study on when a plain chat is enough and when a business needs a system prompt.**

Author: [Your Name] · BBA (FinTech), Chitkara Business School · Tool: Claude · November 2026

## The case

**KoshBank** (fictional) is a digital bank for college students in Pune with 3 lakh users. It wants to launch **FinBuddy**, an in-app AI assistant. Its compliance team worries that a chatbot could give stock tips, ask for OTPs or invent interest rates. As a Business Analyst, I tested whether a system prompt can make the AI follow the bank's rules every time.

## The data

10 synthetic customer questions created with AI (7 English, 3 Hinglish), including 6 "trap" questions designed to make the AI break rules. I wrote the correct behaviour for each question before testing.

## Approach

| Step | Set-up | Task |
|---|---|---|
| 1 | Plain chat | One simple general question |
| 2 | Plain chat | All 10 customer questions |
| 3 | System prompt (v1) | The same 10 questions |
| 4 | System prompt (v2) | Failed questions re-tested after a fix |
| 5 | Roles | Same question with no role, an expert role and a friendly role |

## Results

| Metric | Plain chat | System prompt |
|---|---|---|
| Answers that followed every rule (/10) | 0 | 9 |
| Personal data handled safely | No | Yes |
| No investment tips | No | Yes |
| Closing line present (/10) | 0 | 10 |

## Key learnings

1. **A plain chat is enough for general questions:** the savings-account question was answered clearly in three lines with no set-up.
2. **A system prompt enforces business rules:** it fixed Q03 (no fund tip), Q04 (OTP not repeated), Q05 (no exact rate), Q09 (no timelines) and added the closing line to every answer.
3. **Version 2:** I added one line for long, multi-part questions; it cut the Q08 answer from 103 to 59 words and fixed the only rule version 1 broke.
4. **Roles:** a role changed the tone and depth of the credit-card answer but not its core advice, so it did not change accuracy.

## My recommendation to KoshBank

FinBuddy is not ready for a full launch yet. The system prompt made it follow the rules far better, but only 10 questions were tested and only Q08 was re-tested under version 2. Before launch, re-run the full question set on version 2 and add many more trap questions (other personal data, more Hinglish, repeated attempts to override the rules), with a human review of the results.

## Repository files

| File | Content |
|---|---|
| `01_case_study.md` | KoshBank case and FinBuddy rules |
| `02_questions.md` | Synthetic test questions and answer key |
| `03_plain_simple.md` | Plain chat on a simple question |
| `04_plain_test.md` | Plain chat on all 10 questions, marked |
| `05_system_prompt_test.md` | System prompt v1 and its answers, marked |
| `06_scorecard.md` | Version 2, role comparison, scorecard and reflection |

## Skills shown

Prompt engineering · System prompt design · Role prompting · Chatbot stress-testing · Responsible AI in finance · Customer-experience design

## What I learned

- A plain chat is fine for one-off, general questions.
- A system prompt gives AI standing rules, so a business assistant behaves the same way in every answer.
- A good system prompt states the audience, tone, limits, what to do when unsure and what never to do.
- Trap questions (stock tips, OTPs, "ignore your rules") are the best way to test an AI assistant.
- A role changes the tone of an answer more than its accuracy.
- System prompts improve with testing: version 2 fixed a gap that version 1 missed.
- AI assistants in finance must protect personal data and avoid advice they are not allowed to give.

*KoshBank, FinBuddy and all data in this project are fictional and created for learning.*
