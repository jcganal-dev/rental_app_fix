- ### One of the fixes made:
    I addressed the rule preventing the booking of equipment under maintenance (Task 3). Previously, the API returned all items regardless of their status without any filtering. To fix this, I added validation on the backend to immediately reject any booking requests for equipment marked under maintenance. On the frontend, rather than completely hiding these items (which might mislead customers into thinking we don't carry them), I kept them in the list but disabled the selection and labeled them accordingly. This enforces the rule securely at the API level while keeping the UI transparent.

- ### Previous failure:
    A booking for Jan 9, 2026 to Jan 17, 2026 which was overlapping with Jan 10, 2026 to Jan 15, 2026 was wrongly allowed
    
- ### AI Use:
   I only used AI to quickly check if there was a built-in Python function for calculating date collisions that I didn't know about (there wasn't). While I use AI almost every day for coding and research, these specific bugs were straightforward. Since there wasn't a strict time constraint, sending the whole repository for an LLM to process felt unnecessary and wasteful, so I just manually traced the logic errors myself.