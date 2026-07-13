# Data Visualization (Charts) Skills & Resources

Libraries for rendering data-driven charts and dashboards — bar/line/pie/scatter plots, statistical graphics, and interactive exploratory visualizations. Use these when a task calls for representing tabular or time-series data visually, as opposed to freeform diagrams or illustrations.

## Best Repositories

### [Chart.js](https://github.com/chartjs/Chart.js)
- **Stars:** ~67,600 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-05-27

Chart.js is a simple, well-documented HTML5 `<canvas>` charting library covering the eight most common chart types (line, bar, radar, doughnut/pie, polar area, bubble, scatter, area) with built-in animation and responsiveness.

Best for lightweight, dependency-free dashboards and educational charts where you want sensible defaults and a gentle learning curve rather than full low-level control.

**Installation:**
```bash
npm install chart.js
```
```html
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
```

**Usage example:**
```javascript
import { Chart } from 'chart.js/auto';

new Chart(document.getElementById('myChart'), {
  type: 'bar',
  data: {
    labels: ['Red', 'Blue', 'Yellow'],
    datasets: [{ label: 'Votes', data: [12, 19, 3] }]
  }
});
```

### [Apache ECharts](https://github.com/apache/echarts)
- **Stars:** ~66,800 (as of 2026-07-13)
- **License:** Apache-2.0
- **Last updated:** actively maintained, last push 2026-07-01

Apache ECharts is a powerful, GPU-accelerated (Canvas/SVG) charting library with an enormous catalog of chart types — from standard bar/line/pie to geographic maps, 3D, and graph/network visualizations — plus rich built-in interaction (brushing, data zoom, tooltips).

Best for feature-rich, highly interactive dashboards and scientific/statistical visualizations that need chart types beyond the basics (heatmaps, Sankey, treemaps, geo maps).

**Installation:**
```bash
npm install echarts
```
```html
<script src="https://cdn.jsdelivr.net/npm/echarts@5/dist/echarts.min.js"></script>
```

**Usage example:**
```javascript
import * as echarts from 'echarts';

const chart = echarts.init(document.getElementById('main'));
chart.setOption({
  xAxis: { type: 'category', data: ['Mon', 'Tue', 'Wed'] },
  yAxis: { type: 'value' },
  series: [{ data: [120, 200, 150], type: 'bar' }]
});
```

### [Plotly.js](https://github.com/plotly/plotly.js)
- **Stars:** ~18,250 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-10

Plotly.js is a high-level, declarative charting library (built on D3 and WebGL/regl) offering 40+ chart types, including scientific and statistical charts (contour plots, 3D surfaces, candlesticks), with built-in zoom/pan/export interactivity. It's the JS engine behind Plotly and Dash.

Best for scientific/statistical educational charts (regression lines, error bars, 3D surfaces) where publication-quality interactive output matters.

**Installation:**
```bash
npm install plotly.js-dist-min
```
```html
<script src="https://cdn.plot.ly/plotly-2.35.2.min.js"></script>
```

**Usage example:**
```javascript
import Plotly from 'plotly.js-dist-min';

Plotly.newPlot('chart', [{
  x: [1, 2, 3, 4],
  y: [10, 15, 13, 17],
  type: 'scatter'
}]);
```

### [Recharts](https://github.com/recharts/recharts)
- **Stars:** ~27,300 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-07-13

Recharts is a composable charting library built with React and D3, exposing charts as declarative React components (`<LineChart>`, `<Bar>`, `<XAxis>`, etc.) rather than an imperative config object.

Best for React apps/dashboards where charts need to feel like native React components — easy to theme, compose, and integrate with app state.

**Installation:**
```bash
npm install recharts
```

**Usage example:**
```jsx
import { LineChart, Line, XAxis, YAxis, CartesianGrid } from 'recharts';

const data = [{ name: 'A', value: 10 }, { name: 'B', value: 25 }];

function MyChart() {
  return (
    <LineChart width={400} height={200} data={data}>
      <CartesianGrid stroke="#eee" />
      <XAxis dataKey="name" />
      <YAxis />
      <Line type="monotone" dataKey="value" stroke="#8884d8" />
    </LineChart>
  );
}
```

### [visx](https://github.com/airbnb/visx)
- **Stars:** ~20,940 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, last push 2026-06-22

visx (built by Airbnb) provides low-level, unopinionated D3-powered visualization primitives (scales, shapes, axes, groups) as individual React components, rather than pre-built chart types — you compose your own chart from parts.

Best for fully custom, highly polished educational charts where you need D3's flexibility but want React's rendering/DOM-diffing instead of manual D3 selections.

**Installation:**
```bash
npm install @visx/shape @visx/scale @visx/group @visx/mock-data
```

**Usage example:**
```jsx
import { Group } from '@visx/group';
import { Bar } from '@visx/shape';
import { scaleLinear, scaleBand } from '@visx/scale';

const data = [{ letter: 'A', frequency: 0.08 }, { letter: 'B', frequency: 0.02 }];
const xScale = scaleBand({ range: [0, 400], domain: data.map(d => d.letter), padding: 0.4 });
const yScale = scaleLinear({ range: [200, 0], domain: [0, 0.1] });

function BarGraph() {
  return (
    <svg width={400} height={200}>
      <Group>
        {data.map(d => (
          <Bar
            key={d.letter}
            x={xScale(d.letter)}
            y={yScale(d.frequency)}
            width={xScale.bandwidth()}
            height={200 - yScale(d.frequency)}
            fill="#fc2e1c"
          />
        ))}
      </Group>
    </svg>
  );
}
```

### [ApexCharts](https://github.com/apexcharts/apexcharts.js)
- **Stars:** ~15,100 (as of 2026-07-13)
- **License:** Dual-license — free "Community License" for individuals/non-profits/educators/small businesses (<$2M annual revenue); paid Commercial/OEM license required above that threshold. **Not MIT/Apache/BSD** — verify eligibility for your use case at [apexcharts.com/license](https://apexcharts.com).
- **Last updated:** actively maintained, last push 2026-07-09

ApexCharts is a modern, interactive SVG-based charting library with strong out-of-the-box styling, animations, and gradient support, covering line/bar/area/candlestick/radar and more.

Best for polished, visually rich interactive dashboards where design quality matters — but check the license tier for your organization's revenue before adopting commercially.

**Installation:**
```bash
npm install apexcharts
```

**Usage example:**
```javascript
import ApexCharts from 'apexcharts';

const chart = new ApexCharts(document.querySelector("#chart"), {
  chart: { type: 'bar' },
  series: [{ name: 'sales', data: [30, 40, 45, 50] }],
  xaxis: { categories: ['Jan', 'Feb', 'Mar', 'Apr'] }
});
chart.render();
```

### [Observable Plot](https://github.com/observablehq/plot)
- **Stars:** ~5,300 (as of 2026-07-13)
- **License:** ISC
- **Last updated:** v0.6.17 released 2025-02-14

Observable Plot is a concise, D3-based JavaScript library implementing a layered grammar-of-graphics API, optimized for fast exploratory data visualization from tabular data with minimal code.

Best for quick exploratory charts and educational data-analysis notebooks where terse, expressive syntax (`Plot.dot`, `Plot.line`, `Plot.barY`, ...) is preferred over verbose configuration.

**Installation:**
```bash
npm install @observablehq/plot
```
```html
<script src="https://cdn.jsdelivr.net/npm/@observablehq/plot@0.6/dist/plot.umd.min.js"></script>
```

**Usage example:**
```javascript
import * as Plot from "@observablehq/plot";

const chart = Plot.barY(data, { x: "category", y: "value" }).plot();
document.body.append(chart);
```

## Notes

- **ApexCharts is not permissively licensed** for larger commercial users — it uses a revenue-based dual-license model. Prefer Chart.js, ECharts, Plotly.js, Recharts, or visx if a pure MIT/Apache footprint is a hard requirement.
- **Observable Plot** has a smaller star count and slower release cadence than the others but is maintained by the Observable/D3 team and is commonly recommended for grammar-of-graphics style exploratory charts.
- All of these libraries build on or interoperate with **D3.js** (see the Graphics category), which remains the lowest-level building block for custom visualization work.

## License Summary

| Repository | License |
|---|---|
| [Chart.js](https://github.com/chartjs/Chart.js) | MIT |
| [Apache ECharts](https://github.com/apache/echarts) | Apache-2.0 |
| [Plotly.js](https://github.com/plotly/plotly.js) | MIT |
| [Recharts](https://github.com/recharts/recharts) | MIT |
| [visx](https://github.com/airbnb/visx) | MIT |
| [ApexCharts](https://github.com/apexcharts/apexcharts.js) | Dual (Community/Commercial, non-permissive) |
| [Observable Plot](https://github.com/observablehq/plot) | ISC |
