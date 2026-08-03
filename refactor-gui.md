Redesign the wizard progress bar (stepper) of the "New execution" modal. It has 3 steps:
1. "Repository & branch"
2. "Environment & configuration"
3. "Test cases"

Requirements:

LAYOUT
- Horizontal stepper centered at the top of the modal, below the modal title, above the step content.
- Each step: a 30px circle with the step state, and a short label centered UNDER the circle (12px, max 150px wide, text-align center).
- Between circles: a horizontal connector line, 3px tall, rounded, flex:1 so it stretches, vertically aligned with the center of the circles.

STEP STATES
- Completed step: solid green circle (#1c8a52), white checkmark "✓" instead of the number, label in green (#1c8a52), font-weight 600. Connector line after a completed step is solid green.
- Current step: white circle with a 3px green border (#1c8a52), the step number in green bold, label in dark text (#22302a) font-weight 700.
- Future step: light gray circle (#e3e8e5) with gray number (#93a29a), gray label, gray connector (#e3e8e5).

BEHAVIOR
- Completed steps are clickable to navigate back; future steps are not clickable.
- Add cursor:pointer and a subtle hover state only on clickable (completed) steps.
- Keep it purely presentational otherwise — the parent wizard controls which step is active via a prop/state (activeStep index).

STYLE
- Font: inherit the app font. No emojis, no icons besides the checkmark.
- Spacing: ~18px vertical padding around the stepper, ~48px horizontal padding so connectors don't touch the modal edges.
- The whole component must be responsive: labels can wrap to 2 lines but circles stay aligned on one row.

Do not change any other part of the modal in this task.