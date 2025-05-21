# 📱 Project Overview  
**Objective**: Stress-test Instagram's recommendation system to analyze:  
- Effectiveness of "Not Interested" feedback  
- Inconsistencies across content categories
- Proposed UX improvements  

# 🔍 Key Findings  
| Test Case               | Expected Outcome       | Actual Result          |  
|-------------------------|------------------------|------------------------|  
| Liked 3 animal Reels    | More animal content    | ✅ Flooded feed        |  
| "Not Interested" x1     | Reduced animal Reels   | ❌ Increased frequency |  
| "Not Interested" x2     | Significant reduction  | ❌ No change           |  

**Critical Insight**:  
Negative signals are either ignored or misclassified as engagement for viral content types.

# 🛠️ Proposed Solutions  
1. **Signal Rebalancing**  
   - Weight "Not Interested" 3x heavier than likes  
2. **Granular Controls**  
   - [Figma prototype] of Sensitivity Slider  
3. **Transparency Features**  
   - User-facing explanation of algorithmic actions
