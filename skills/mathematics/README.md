# Mathematics Skills & Resources

Curated, mature open-source libraries for math typesetting, symbolic computation, interactive geometry/plotting, and mathematical animation. Use these when building math-education tools, interactive quizzes, function/graph visualizations, or rendering LaTeX/math notation on the web.

## Best Repositories

### [KaTeX](https://github.com/KaTeX/KaTeX)
- **Stars:** ~20,200 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits as of 2026-07-13

Fast, synchronous math-typesetting library for the web that renders LaTeX/TeX notation to HTML+CSS without a server round-trip. Best for embedding math notation in any web page, quiz, or documentation with minimal render latency.

**Installation:**
```bash
npm install katex
```

**Usage example:**
```javascript
import katex from "katex";
import "katex/dist/katex.min.css";

katex.render("c = \\pm\\sqrt{a^2 + b^2}", document.getElementById("math"));
```

### [MathJax](https://github.com/mathjax/MathJax)
- **Stars:** ~10,900 (as of 2026-07-13)
- **License:** Apache-2.0
- **Last updated:** actively maintained, commits as of 2026-07-13

Beautiful, accessible math display engine supporting LaTeX, MathML, and AsciiMath in all browsers, with strong screen-reader/accessibility support. Best when accessibility and broad notation-format support matter more than raw render speed (complements KaTeX rather than replacing it).

**Installation:**
```html
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
```

**Usage example:**
```html
<p>Euler's identity: \( e^{i\pi} + 1 = 0 \)</p>
```

### [mathjs](https://github.com/josdejong/mathjs)
- **Stars:** ~15,057 (as of 2026-07-13)
- **License:** Apache-2.0
- **Last updated:** actively maintained, commits as of 2026-07-13

An extensive math library for JavaScript and Node.js supporting numbers, big numbers, complex numbers, matrices, units, and a flexible expression parser/evaluator. Best for building calculators, linear-algebra tools, unit-conversion widgets, and general numeric computation in JS.

**Installation:**
```bash
npm install mathjs
```

**Usage example:**
```javascript
import { create, all } from "mathjs";
const math = create(all);

math.evaluate("sqrt(3^2 + 4^2)"); // 5
math.evaluate("det([[1, 2], [3, 4]])"); // -2
```

### [JSXGraph](https://github.com/jsxgraph/jsxgraph)
- **Stars:** ~1,379 (as of 2026-07-13)
- **License:** Dual-licensed LGPL / MIT
- **Last updated:** actively maintained, commits as of 2026-07-13

Cross-browser library for interactive geometry, function plotting, charting, and data visualization, rendering to SVG, VML, or canvas. Best for building interactive geometry constructions, coordinate-system diagrams, and draggable trigonometry/calculus visualizations directly in the browser.

**Installation:**
```bash
npm install jsxgraph
```

**Usage example:**
```javascript
const board = JXG.JSXGraph.initBoard('jxgbox', { boundingbox: [-5, 5, 5, -5], axis: true });
board.create('functiongraph', [(x) => Math.sin(x)]);
board.create('point', [1, 1], { name: 'A' });
```

### [SymPy](https://github.com/sympy/sympy)
- **Stars:** ~14,700 (as of 2026-07-13, via web verification)
- **License:** BSD-3-Clause
- **Last updated:** actively maintained

A full computer algebra system (CAS) written in pure Python for symbolic algebra, calculus, differential equations, number theory, and linear algebra. Best when you need exact symbolic manipulation (derivatives, integrals, equation solving) rather than numeric approximation.

**Installation:**
```bash
pip install sympy
```

**Usage example:**
```python
from sympy import symbols, diff, integrate, solve

x = symbols('x')
diff(x**3 + 2*x, x)          # 3*x**2 + 2
integrate(x**2, x)            # x**3/3
solve(x**2 - 4, x)             # [-2, 2]
```

### [Manim (Community Edition)](https://github.com/ManimCommunity/manim)
- **Stars:** ~39,491 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits as of 2026-07-13

Community-maintained Python framework for precise, programmatic mathematical animations, forked from 3Blue1Brown's original engine. Best for producing explanatory math-video animations (geometry, calculus, vector fields). Note: the original [3b1b/manim](https://github.com/3b1b/manim) (~88,440 stars, MIT) is the upstream research-video engine but is less API-stable/documented for general use — the Community Edition is recommended for reuse and has clearer docs.

**Installation:**
```bash
pip install manim
```

**Usage example:**
```python
from manim import *

class SquareToCircle(Scene):
    def construct(self):
        square = Square()
        circle = Circle()
        self.play(Create(square))
        self.play(Transform(square, circle))
```

### [function-plot](https://github.com/mauriciopoppe/function-plot)
- **Stars:** ~1,000 (as of 2026-07-13, via web verification)
- **License:** MIT
- **Last updated:** actively maintained

A versatile 2D function plotter built on top of D3.js that renders functions (including derivatives) with minimal configuration. Best for quick, lightweight function-graphing widgets (calculus/derivative visualizations) without hand-rolling D3 code.

**Installation:**
```bash
npm install function-plot
```

**Usage example:**
```javascript
import functionPlot from 'function-plot'

functionPlot({
  target: '#root',
  data: [
    {
      fn: 'x^2',
      derivative: { fn: '2*x', updateOnMouseMove: true }
    }
  ]
})
```

### [D3.js](https://github.com/d3/d3)
- **Stars:** ~113,208 (as of 2026-07-13)
- **License:** ISC
- **Last updated:** actively maintained, commits as of 2026-07-13

Low-level data-visualization library for binding data to SVG/Canvas/HTML and driving it with powerful scales, shapes, and transitions. Best as the foundation layer when you need fully custom coordinate systems, statistics charts, or bespoke math diagrams that off-the-shelf plotting libraries can't express.

**Installation:**
```bash
npm install d3
```

**Usage example:**
```javascript
import * as d3 from "d3";

const scale = d3.scaleLinear().domain([0, 100]).range([0, 500]);
d3.select("svg")
  .selectAll("circle")
  .data([10, 20, 30])
  .join("circle")
  .attr("cx", d => scale(d))
  .attr("r", 5);
```

## Notes
- KaTeX and MathJax are complementary, not competing: KaTeX is faster and simpler; MathJax supports more input formats (MathML, AsciiMath) and stronger accessibility. Many projects ship both and pick per use case.
- JSXGraph's dual LGPL/MIT license means you may choose whichever term suits your project; treat it as MIT-compatible for permissive use.
- `3b1b/manim` (the original engine behind 3Blue1Brown's videos) is MIT-licensed and has far more stars than the Community Edition, but is explicitly documented by its own maintainers as less stable/less suited to general reuse — prefer `ManimCommunity/manim` unless you specifically need parity with 3Blue1Brown's videos.
- Star counts for SymPy and function-plot were confirmed via web search rather than the GitHub API (rate-limited at verification time); treat as approximate.

## License Summary
| Repository | License |
|---|---|
| [KaTeX](https://github.com/KaTeX/KaTeX) | MIT |
| [MathJax](https://github.com/mathjax/MathJax) | Apache-2.0 |
| [mathjs](https://github.com/josdejong/mathjs) | Apache-2.0 |
| [JSXGraph](https://github.com/jsxgraph/jsxgraph) | LGPL / MIT (dual) |
| [SymPy](https://github.com/sympy/sympy) | BSD-3-Clause |
| [Manim (Community)](https://github.com/ManimCommunity/manim) | MIT |
| [function-plot](https://github.com/mauriciopoppe/function-plot) | MIT |
| [D3.js](https://github.com/d3/d3) | ISC |
