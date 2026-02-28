# Question 3 – Prompt Engineering and Verification Evidence

## 1. Prompt 1 – Planning Prompt (No Code)

### Prompt I Asked ChatGPT

I am building a responsive website using HTML and CSS only (no frameworks).  
I need to implement responsive breakpoints for desktop, tablet, and mobile.  
Desktop should have a 4-column grid, tablet 2 columns, and mobile 1 column.  
The hero section should display in two columns on desktop and stack vertically on mobile.  
The header should have the logo on the left and navigation on the right for desktop, and stacked/centered on mobile.  
Please give me a structured implementation plan only (no code).

---

### Two Things I Accepted From the Plan

1. **Using Flexbox for layout control**  
   I accepted using `display: flex` for the header and hero section because it allows easy switching between horizontal and vertical layouts using `flex-direction`.

2. **Using two breakpoints (900px and 600px)**  
   I accepted the recommendation to use `@media (max-width: 900px)` for tablet and `@media (max-width: 600px)` for mobile. This directly supports the required 4 → 2 → 1 column grid layout.

---

### One Thing I Rejected (and Why)

The plan suggested implementing a hamburger menu for mobile navigation.  
I rejected this suggestion because the assignment specifies HTML and CSS only, and a hamburger toggle would require JavaScript. The rubric did not require interactive navigation.

---

## 2. Prompt 2 – Debug Prompt

### Problem Statement

When resizing the browser to mobile width (under 600px), the hero section did not stack vertically. The hero card stayed beside the text instead of moving underneath it.

---

### CSS Snippet I Asked About

```css
.hero {
  display: flex;
  justify-content: space-between;
}

@media (max-width: 600px) {
  .hero {
    text-align: center;
  }
}
Most Important Part of the AI Response

The AI explained that changing text-align does not affect the layout direction of flex items.
It stated that I must explicitly change the flex direction inside the mobile media query by adding:

flex-direction: column;

What I Changed Afterward

I updated my CSS to:

@media (max-width: 600px) {
  .hero {
    flex-direction: column;
    text-align: center;
  }
}

After this change, the hero section correctly stacked vertically on mobile screens.
3. Verification List
Viewport Sizes Tested

375px (Mobile)

768px (Tablet)

1200px (Desktop)

What I Checked Visually

At 1200px (Desktop):

Logo aligned left and navigation aligned right

Hero displayed in two columns

Grid displayed 4 columns

No horizontal overflow

At 768px (Tablet):

Grid switched to 2 columns

Hero remained in two columns

Header remained horizontal

At 375px (Mobile):

Navigation stacked vertically and centered

Hero stacked vertically

Grid displayed 1 column

No layout overflow or spacing issues
