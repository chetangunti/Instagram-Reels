# Instagram Reels Algorithm Teardown  
## Why the "Not Interested" Signal Fails for Viral Content

---

## Project Objective  
This case study investigates how Instagram’s Reels recommendation algorithm reacts to negative feedback like “Not Interested” especially when applied to viral content like animal videos.  
Despite explicitly expressing disinterest, users often receive **more** of the same content, leading to a poor feedback experience and possible platform fatigue.

---

## 🔍 Key Findings

| Action                     | Expected Behavior         | Actual Behavior           | Severity   |
|----------------------------|---------------------------|---------------------------|------------|
| 👍 Like 3 animal Reels     | More animal Reels         | ✅ Flooded the feed       | Low        |
| 🚫 1x "Not Interested"     | Fewer animal Reels        | ❌ Content increased       | High       |
| ❌ 2 Dislikes              | Drastic reduction         | ❌ No change               | Critical   |


> **Insight**: Instagram’s algorithm appears to treat *any engagement*, even negative, as a signal to show more of the same — especially for high-retention content like animals if they are initially interested.

---

## Proposed Solutions

### 1. **Signal Rebalancing**
- Treat "Not Interested" as 3x the weight of a Like  
- Add a decay timer: Dislikes expire after 7 days to allow user behavior to evolve  

### 2. **Sensitivity Slider (UX Feature)**
- New user setting to control strictness of “Not Interested” signals  
- Options: **Lenient → Moderate → Strict (nuclear option)**  
- See [Figma Prototype](https://github.com/chetangunti/Instagram-Reels/blob/39f2c2faff7b15ff4eda764905df9381f83ead4c/design/Suggested%20Change.png)

### 3. **Transparency Feedback Loop**
- Show confirmation when user preferences are updated  
- Make it clear what happens after "Not Interested" is tapped

---

## Repository Structure

| File/Folder                         | Description                                      |
|------------------------------------|--------------------------------------------------|
| `research/test_plan.md`            | Hypothesis, methodology, and raw test logs       |
| `research/reddit_quotes.md`        | User complaints confirming broken feedback loop  |
| `design/user_flow_mermaid.md`      | Mermaid diagram of the improved UX flow          |
| `design/suggested change.fig`    | Figma file for the proposed slider UI            |
| `business_impact.md`               | Retention, ad, and fairness impact analysis      |

---

## Business Relevance

### The Problem
- 68% of users leave platforms that ignore their preferences (Pew Research)
- Broken feedback loops lead to mismatched content and lower engagement

### The Value of Fixing It
| Area               | Impact                                      |
|--------------------|---------------------------------------------|
| Retention          | +8% 30-day retention (projected)            |
| Ad Relevance       | +12% CTR via better signal accuracy         |
| Creator Fairness   | Increased exposure for niche creators       |
| Engineering Effort | ~2 sprints to build (uses existing infra)   |

See full breakdown in [`business_impact.md`](https://github.com/chetangunti/Instagram-Reels/blob/39f2c2faff7b15ff4eda764905df9381f83ead4c/research/business_impact.md)

---

## Product & PM Skills Demonstrated

- Customer empathy (through Reddit/user complaints)
- Structured testing and logging methodology
- UX solution ideation (Sensitivity Slider)
- Data-backed impact modeling
- Clear articulation of user pain + design fixes

---

## 🚀 How You Can Contribute

1. Run similar tests on your own Instagram or TikTok account
2. Suggest new test cases via Issues
3. Fork the repo and create your own teardown with a different focus (e.g., fitness, parenting, travel)

```bash
# Example: Log content interaction manually
$ python log_action.py --action "not_interested" --content_type "travel"
