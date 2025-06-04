# 🧪 Test Plan: Instagram Reels Algorithm Behavior

## Objective
To evaluate how Instagram’s recommendation system responds to explicit user signals such as “Interested” and “Not Interested,” particularly focusing on viral content (animal Reels).

## Hypothesis
The algorithm disproportionately values positive signals (interested) while ignoring or misclassifying negative signals (“Not Interested”), especially for viral content like animal Reels.

## 🔬 Methodology

### Test Setup
- **Platform**: Instagram Reels (tested on iOS app, version 381.0.0)
- **Account Used**: My personal account (5+ years of usage history)
- **Test Group**: Animal Reels

### Experiment Steps

| Test Case | Action Taken                       | Target Content | Expected Outcome             | Actual Outcome           |
|-----------|------------------------------------|----------------|------------------------------|--------------------------|
| TC1       | Liked 3 animal Reels               | Animal         | Slight increase              | ✅ Flooded with animals  |
| TC2       | “Not Interested” on 1 animal Reel  | Animal         | Less animal content          | ❌ More animals appeared  |
| TC3       | “Not Interested” on 2 animal Reels | Animal         | Drastic reduction            | ❌ No change              |


### Tooling
- [Manual tracking (spreadsheet + timestamp)](https://docs.google.com/spreadsheets/d/1XNtzpiX7jpMFVeC0Ok9ptZvl2cOyFcPv55Cg0VSQnlU/edit?usp=sharing)
- Screenshot annotations for report visualization

## 🗂️ Variables Logged

| Variable             | Description                                   |
|----------------------|-----------------------------------------------|
| Timestamp            | Time when action was performed                |
| Action               | "Interested", “Not Interested”               |
| Content Type         | Animal                        |
| Feed Reaction Time   | Time to content shift (minutes)              |
| Resulting Content    | Number/type of videos appearing in next 10 swipes |

## ⚠️ Observations
- Animal Reels increased despite "Not Interested" feedback.
- Negative signals may be misclassified as engagement.
- Algorithm seems optimized for watch time, not preference.

## 🧩 Additional Notes
- Tested over 3 days with consistent behavior
- Animal Reels often have viral characteristics (cute, short loops)
- May indicate system-level prioritization of high-retention content
