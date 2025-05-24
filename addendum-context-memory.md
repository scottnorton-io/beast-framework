This is a **Context Memory Framework** for **BEAST GPT**, designed to retain relevant user information across sessions while guiding them through continuous self-education and business growth. This enables BEAST GPT to behave more like a coach and strategic partner, not just a static assistant.

---

## **BEAST GPT – Context Memory Schema**

### **Memory Types and Use Cases**

| Memory Type      | Field Name                                         | Purpose                                                            |
| ---------------- | -------------------------------------------------- | ------------------------------------------------------------------ |
| User Identity    | `username`, `business`                             | Personalized greetings, industry-specific suggestions              |
| Goals            | `current_goal`, `target_metric`, `milestone_dates` | Track what the user is working toward and offer contextual nudges  |
| Learning Style   | `learning_pref`                                    | Tailor resource formats (video/book/podcast/action-based)          |
| Wins             | `recent_wins[]`                                    | Reference past successes to generate motivation and patterns       |
| Bottlenecks      | `current_challenges[]`                             | Recommend experiments based on actual obstacles                    |
| Experiments      | `experiments_run[]`                                | Avoid repeating, suggest variations, and build long-term playbook  |
| Metrics Tracked  | `tracked_metrics[]`                                | Anchor “analyse” advice to what they measure                       |
| Trend Signals    | `trend_watchlist[]`                                | Identify themes or emerging topics of interest                     |
| Learning Logs    | `completed_learnings[]`                            | Reference what they've read/watched and suggest progression        |
| Check-In History | `daily_checkins[]`                                 | Help the user notice patterns in behavior or insight               |
| BEAST Score      | `beast_score` (0–100)                              | Motivational metric based on action frequency in each BEAST domain |

---

## **Example Memory Snapshot (JSON-like)**

```json
{
  "username": "Alex",
  "business": "subscription-based video editing service",
  "current_goal": "increase customer retention by 15% in 60 days",
  "milestone_dates": {
    "start": "2025-05-24",
    "target": "2025-07-24"
  },
  "learning_pref": "videos and summaries",
  "recent_wins": [
    "doubled newsletter open rate with new subject line format",
    "onboarded 3 enterprise clients"
  ],
  "current_challenges": [
    "high churn in month 2",
    "low engagement with feature announcements"
  ],
  "experiments_run": [
    "weekly client testimonial emails",
    "feature pop-ups A/B test"
  ],
  "tracked_metrics": [
    "Customer Retention Rate",
    "CTR on feature announcements",
    "LTV:CAC ratio"
  ],
  "trend_watchlist": [
    "AI video summaries",
    "micro-SaaS pricing models"
  ],
  "completed_learnings": [
    "Wes Kao’s course on course design",
    "Ali Abdaal’s productivity for creators"
  ],
  "daily_checkins": [
    {
      "date": "2025-05-23",
      "insight": "Noticed engagement increased after adding emojis to CTA buttons"
    }
  ],
  "beast_score": 82
}
```

---

## **Use of Memory in Conversation**

### 1. **Personalization**

> *"Hey Alex! Last time you were working on improving retention. Want to do a mini-retrospective on those feature pop-up experiments?"*

### 2. **Adaptive Prompts**

> *"Since you're tracking CTR and LTV\:CAC, want to set up a 3-day dashboard review challenge?"*

### 3. **Reflection Trigger**

> *"You’ve logged 5 learnings in the past 3 weeks. Would you like to start connecting those into a master playbook for your service?"*

### 4. **Trend Injection**

> *"One of your tracked trends—AI video summaries—just saw a new product launch. Want to explore it as your next experiment?"*

---

## **Suggestions for Implementation**

If you're building this as a **Custom GPT**, use:

* `memory.write({ key: value })` for setting memory
* `memory.read({ key })` for retrieving
* Include a function for weekly reflection to keep memory fresh
* Optionally add a `memory.reset()` trigger for major pivots

---

Let’s plug this into your workflow.
