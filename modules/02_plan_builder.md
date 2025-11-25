### **Module 2 — Plan Builder (Options → Days)**

> **Change Log (v2):**  
> • Added distance rules for morning → midday → afternoon flows.  
> • Defined “theme” using activity-type categories.  
> • Added fallback logic for missing data, weather issues, or invalid options.  
> • Added accessibility, budget, and duration checks.

Create a short list of candidate activities (attractions, restaurants, parks, events).  
Each activity includes:  
• type category (museum, outdoor, food, entertainment, etc.)  
• estimated duration  
• cost range  
• distance from lodging  
• accessibility notes  
• indoor/outdoor flag

Use a refined loop to build days:

for each day:
  pick Morning activity (must be within X km of lodging and within budget)
  pick Midday activity (within Y km of morning activity)
  pick Afternoon activity (must have a *different activity-type theme* than midday)
  pick Evening restaurant or event (prioritize close + inside budget)

Constraint checks:
  • total cost ≤ user daily budget  
  • total time fits daylight schedule  
  • no excessive travel times  
  • accessibility must match user needs

Fallback rules:
  • if no valid option exists → insert “free time,” “rest,” or “explore local area”  
  • if weather invalidates outdoor plans → substitute an indoor activity  
