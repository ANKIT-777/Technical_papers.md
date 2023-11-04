# CSS 

**1. Selectors:**
   - Element Selector: `p { color: blue; }`
   - Class Selector: `.highlight { background: yellow; }`
   - ID Selector: `#header { font-size: 24px; }`

**2. Properties and Values:**
   - `font-family`: `font-family: Arial, sans-serif;`
   - `color`: `color: #FF0000;`
   - `background-color`: `background-color: #F0F0F0;`

**3. Inline CSS:**
   - `<p style="color: green;">This is a green text.</p>`

**4. Internal CSS:**
   ```html
   <style>
     h1 { font-size: 36px; }
     .info { background-color: #EFEFEF; }
   </style>
   ```

**5. External CSS:**
   - Link CSS file in HTML: `<link rel="stylesheet" type="text/css" href="styles.css">`

**6. Text Styling:**
   - `font-size`: `font-size: 18px;`
   - `font-weight`: `font-weight: bold;`

**7. Background:**
   - `background-color`: `background-color: #FFD700;`
   - `background-image`: `background-image: url('bg.jpg');`

**8. Box Model:**
   - `padding`: `padding: 10px;`
   - `border`: `border: 1px solid #333;`

**9. Flexbox:**
   ```css
   .container {
     display: flex;
     justify-content: space-between;
   }
   ```

**10. Grid:**
   ```css
   .grid-container {
     display: grid;
     grid-template-columns: 1fr 1fr;
   }
   ```

**11. Transitions:**
   ```css
   .button {
     transition: background-color 0.3s ease;
   }
   .button:hover {
     background-color: #3498db;
   }
   ```

**12. Media Queries:**
-Employ media queries to apply styles based on screen characteristics.
-Define breakpoints to target specific screen sizes.

   ```css
   @media (max-width: 768px) {
     /* Styles for screens up to 768px width */
   }
   ```

**13. Pseudo-classes:**
   - `:hover`: `a:hover { color: #FF6600; }`
   - `:nth-child`: `li:nth-child(odd) { background: #F0F0F0; }`

**14. CSS Preprocessors:**
   - SASS:
     ```scss
     $primary-color: #3498db;
     .button {
       background-color: $primary-color;
     }
     ```

**15. Responsive Design:**
   - Media Query Example:
     ```css
     @media (max-width: 600px) {
       /* Styles for small screens */
     }
     ```


     
