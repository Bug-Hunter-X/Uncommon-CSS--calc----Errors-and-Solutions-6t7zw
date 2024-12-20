# Uncommon CSS `calc()` Errors and Solutions

This repository demonstrates some uncommon errors that can occur when using the CSS `calc()` function and provides solutions to avoid them.

**Common Problems with `calc()`:**

1. **Missing Spaces:**  The `+` and `-` operators in `calc()` require spaces around them.  Forgetting these spaces results in unexpected behaviour.
2. **Invalid Units:** Mixing incompatible units in a calculation will lead to errors.
3. **Division by Zero:** Attempting to divide by zero will cause an error.

**Example (bug.css):**
```css
.box {
  width: calc(100px+50px); /* Correct */
  height: calc(200px- 50px); /* Incorrect, Missing space */
  margin:calc(100%/0); /* Incorrect, division by zero */
  padding:calc(100px+50%); /* Correct */
}
```

**Solution (bugSolution.css):**
```css
.box {
  width: calc(100px + 50px);
  height: calc(200px - 50px);
  margin: 0; /* Avoid division by zero by setting a valid value */
  padding:calc(100px + 50%);
}
```