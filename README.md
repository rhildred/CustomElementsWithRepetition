# Nested looping with a template literal
## used inside a custom element

This is like a for loop without a closing brace. The 2nd line is nested in the first.

```javascript
        class ForEachExample extends HTMLElement {
            connectedCallback() {
                /* 
                  Template literals for-loop example
                  Using `Array(5).join(0).split(0)`, we create an empty array 
                  with 5 items which we can iterate through using `.map()`
                */

                this.innerHTML = `
  <h1>To those who buy groceries ... </h1>
  ${Array(10).join(0).split(0).map((item, i) => `
    <div>If I told you once I told you ${i + 1} ... I love Vivas!!!!.</div>
    ${Array(10).join(0).split(0).map((item, j) => `${j != 0?', ':''}(${i},${j})`).join('')}
  `).join('')}
`
            }
        }

        customElements.define("x-for-each", ForEachExample);

```