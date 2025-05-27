# User Flow: "Not Interested" Interaction with Proposed Enhancements
## Flow Logic: Enhanced "Not Interested" Interaction

Instead of simply hiding a post and making assumptions about the user's preferences, the system now **asks for clarification** when a user taps "Not Interested."

The flow offers:
- **Quick-tap reasons** like:
  - "Don't suggest posts from this account" (existing Instagram UX)
  - "This post made me uncomfortable" (existing Instagram UX)
  - "Manage content preferences" (existing Instagram UX)
  - "Don't suggest posts with certain words"(Delete this Option) → This is    
    too technical or vague for most users
 We introduce a new option:

### Sensitivity Slider (New UX Feature)

- Allows users to define how aggressively Instagram should suppress similar content:
  - **Lenient**: Light reduction
  - **Moderate**: Balance of flexibility and filtering
  - **Strict**: Aggressive suppression (nuclear option)

Once the user adjusts the slider:
- The system recalibrates the weight of the “Not Interested” signal
- A **decay timer** ensures preferences evolve over time (e.g., reset after 7 days)

The flow ends with a **confirmation message**:
> “Thanks! Your preferences have been saved.”

This approach:
- Reduces false positives (e.g., hiding things due to accidental taps)
- Increases user trust by making the process transparent
- Aligns algorithm behavior with actual user intent


![Improved User Flow](./Improved%20User%20Flow.svg)





