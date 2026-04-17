# Todo Card Component - Stage 1a

A responsive, interactive, and stateful todo card component built with HTML, CSS, and Vanilla JavaScript. Developed as part of the Frontend Wizards pipeline (Stage 1a).

## Recent Updates & Changes (Stage 1a vs Stage 0)

The initial version of this project was a static, non-functional HTML layout. The updated code transforms the component into an interactive stateful app:

- **State Management**: Introduced a single source of truth `todoState` object in JavaScript to manage the title, description, priority, due date, and status.
- **Interactive Edit Modal**: Added a functional "Edit" button that opens an interactive modal. The form fields dynamically parse the current data, allowing users to update the component with instantly synced DOM reactions.
- **Time/Overdue Logic**: Built a live auto-updating timer that constantly verifies the difference between `Date.now()` and the `dueDate`. It naturally displays days/hours remaining, or reveals an "Overdue" dynamic badge if the time expires.
- **Expand/Collapse Description**: Replaced a statically fixed paragraph height with a "Read more / Show less" toggle functionality, dynamically dropping the CSS clamping restrictions.
- **Status Synchronization**: Implemented immediate bidirectional syncing between the priority dropdown, completion checkbox, and status tags.

## New Design Decisions

- **Dark Theme Refinement**: Tweaked backgrounds and borders to adopt a deeper slate appearance (`#18181b` and `#27272a`), creating a smoother dark mode silhouette and more refined container shadowing.
- **Dynamic Utility Classes**: Priority badges automatically transition color (e.g., Red for High, Green for Low), and the Overdue alert only materializes via `display: flex` when mathematically required.
- **Modal Overlay Integration**: Created an immersive and isolated editing experience via a semi-transparent absolute overlay (`rgba(0, 0, 0, 0.9)` matching the theme layout).

## Accessibility Notes

- **Standardization**: Updated legacy CSS limitations (such as replacing alone `-webkit-line-clamp` with standard `line-clamp`) to remain compliant with strict linters and standards.
- **Input Focus Management**: The Edit Modal automatically hooks `.focus()` to the title input when it opens, ensuring seamless traversal for those using keyboards or screen readers.
- **Semantic Structure**: Prioritized using native form `label` attachments to dropdowns, `datetime-local` elements for accurate date handling, and extensive `data-testid` annotations to detach testing logic from styling implementations.

## Known Limitations

- **Transient State**: The state is stored strictly in client memory. Refreshing the browser page resets the card back to its default hardcoded attributes. There is no LocalStorage or Database backing.
- **Missing Delete Logic**: The UI features a visual "Delete" button, but it is currently a decorative structural requirement without bound teardown logic.

---

## Getting Started

### Prerequisites

- A modern web browser (Chrome, Firefox, Safari, Edge).

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd Testable-todo-item-card
   ```
2. Open `index.html` in your web browser.

## Testing

This project includes extensive `data-testid` nodes ready for automated end-to-end testing with headless runners.

1. Install dependencies (If testing libraries exist in your environment):
   ```bash
   npm install
   ```

2. Run tests:
   ```bash
   npx playwright test
   ```
