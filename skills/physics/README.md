# Physics Skills & Resources

Curated, mature open-source libraries for physics simulation, mechanics, 3D rendering, and interactive scientific visualization. Use these when building interactive physics experiments, canvas/WebGL animations, mechanics/wave demos, or scientific charting for physics data.

## Best Repositories

### [Matter.js](https://github.com/liabru/matter-js)
- **Stars:** ~18,319 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits as of 2026-07-13

A 2D rigid-body physics engine for the web, rendering to canvas, with collisions, constraints, and composite bodies built in. Best for interactive 2D mechanics demos: gravity, collisions, springs, and constraint-based simulations.

**Installation:**
```bash
npm install matter-js
```

**Usage example:**
```javascript
import Matter from 'matter-js';
const { Engine, Render, Runner, Bodies, Composite } = Matter;

const engine = Engine.create();
const box = Bodies.rectangle(400, 200, 80, 80);
const ground = Bodies.rectangle(400, 610, 810, 60, { isStatic: true });
Composite.add(engine.world, [box, ground]);

const render = Render.create({ element: document.body, engine });
Render.run(render);
Runner.run(Runner.create(), engine);
```

### [three.js](https://github.com/mrdoob/three.js)
- **Stars:** ~113,707 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits as of 2026-07-13

Full-featured JavaScript 3D library (WebGL/WebGPU) for rendering 3D scenes, cameras, lights, and materials in the browser. Best for optics demos (lenses, ray tracing visuals), 3D mechanics/field visualizations, and any physics simulation that needs a 3D scene rather than flat canvas.

**Installation:**
```bash
npm install three
```

**Usage example:**
```javascript
import * as THREE from 'three';

const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

const sphere = new THREE.Mesh(new THREE.SphereGeometry(1, 32, 32), new THREE.MeshNormalMaterial());
scene.add(sphere);
camera.position.z = 5;

function animate() {
  requestAnimationFrame(animate);
  sphere.rotation.y += 0.01;
  renderer.render(scene, camera);
}
animate();
```

### [cannon-es](https://github.com/pmndrs/cannon-es)
- **Stars:** ~1,934 (as of 2026-07-13, via web verification)
- **License:** MIT
- **Last updated:** actively maintained (TypeScript fork of the original cannon.js)

A lightweight, actively-maintained 3D physics engine in JavaScript/TypeScript, commonly paired with three.js for rigid-body dynamics. Best for 3D mechanics simulations (falling objects, rigid-body collisions, constraints) that need a physics step alongside a three.js render loop.

**Installation:**
```bash
npm install cannon-es
```

**Usage example:**
```javascript
import * as CANNON from 'cannon-es';

const world = new CANNON.World({ gravity: new CANNON.Vec3(0, -9.82, 0) });
const sphereBody = new CANNON.Body({ mass: 1, shape: new CANNON.Sphere(1) });
sphereBody.position.set(0, 10, 0);
world.addBody(sphereBody);

world.fixedStep(); // advance simulation by 1/60s
```

### [p5.js](https://github.com/processing/p5.js)
- **Stars:** ~23,799 (as of 2026-07-13)
- **License:** LGPL-2.1
- **Last updated:** actively maintained, commits as of 2026-07-13

A beginner-friendly, client-side creative-coding platform (based on Processing) with a simple canvas/animation API. Best for education-focused physics demos (projectile motion, waves, oscillators) where approachability for students matters more than a full physics engine.

**Installation:**
```bash
npm install p5
```

**Usage example:**
```javascript
new p5((p) => {
  let vy = 0;
  let y = 0;
  p.setup = () => p.createCanvas(400, 400);
  p.draw = () => {
    p.background(255);
    vy += 0.5; // gravity
    y += vy;
    if (y > p.height) { y = p.height; vy *= -0.8; } // bounce
    p.circle(200, y, 40);
  };
});
```

### [PhET Interactive Simulations](https://github.com/phetsims) — see [scenery](https://github.com/phetsims/scenery)
- **Stars:** ~framework repos are small (scenery, joist typically <100 stars each); PhET is a large multi-repo org, not a single popular repo
- **License:** MIT (core libraries like `scenery`, `joist`, `dot`, `kite`); **GPL-3.0** for individual simulation source code
- **Last updated:** actively maintained, commits as of 2026-07-13

PhET (University of Colorado Boulder) is the gold-standard collection of free, research-based interactive HTML5 physics/chemistry/math simulations (circuits, waves, projectile motion, states of matter, gravity and orbits, and more), built on its own `scenery` HTML5 scene-graph library. Best as a reference implementation for interactive-experiment UX and as a source of ready-made physics simulations; each simulation lives in its own repo (e.g. `phetsims/projectile-motion`, `phetsims/wave-interference`, `phetsims/circuit-construction-kit-dc`).

**Installation:**
```bash
# Simulations are built from source per PhET's multi-repo dev process; see:
git clone https://github.com/phetsims/scenery.git
git clone https://github.com/phetsims/example-sim.git
```

**Usage example:**
```html
<!-- Reusable scenery library: build a scene graph node -->
<script type="module">
  import { Node, Rectangle } from 'scenery';
  const rootNode = new Node();
  rootNode.addChild(new Rectangle(0, 0, 100, 50, { fill: 'blue' }));
</script>
```

### [Plotly.js](https://github.com/plotly/plotly.js)
- **Stars:** ~18,254 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits as of 2026-07-13

A declarative, WebGL-accelerated charting library (the engine behind Plotly and Dash) supporting scientific chart types (contour plots, 3D surfaces, heatmaps). Best for plotting experiment/sensor data, wave interference patterns, or thermodynamic state diagrams with publication-quality output.

**Installation:**
```bash
npm install plotly.js-dist-min
```

**Usage example:**
```javascript
import Plotly from 'plotly.js-dist-min';

Plotly.newPlot('chart', [{
  x: [0, 1, 2, 3, 4],
  y: [0, 1, 4, 9, 16],
  type: 'scatter'
}], { title: 'Position vs. Time' });
```

### [Sandboxels](https://github.com/R74nCom/sandboxels)
- **Stars:** ~429 (as of 2026-07-13)
- **License:** No OSI-approved license found (GitHub reports `NOASSERTION`) — **flagged, verify terms before reuse**
- **Last updated:** actively maintained, commits as of 2026-07-13

An in-browser falling-sand cellular-automaton simulator with 500+ elements and thousands of physical/chemical reactions (heat, density, electricity, fire, states of matter). Best as inspiration/reference for particle-based physics-and-chemistry sandbox demos — but because it has no clear open-source license, do not vendor or redistribute its code without contacting the author first.

**Installation:**
```bash
git clone https://github.com/R74nCom/sandboxels.git
# open index.html directly in a browser — no build step required
```

**Usage example:**
```text
No package/API — it's a standalone browser game. Open index.html and interact via the in-page UI;
inspect mods/ and the element-definition JS files to see how new physics/chemistry reactions are declared.
```

## Notes
- `cannon-es` is the actively maintained fork of the original (now largely dormant) `cannon.js`; prefer it for new three.js-based projects.
- PhET's simulation-specific source code is GPL-3.0 (copyleft — any distributed modifications must be open-sourced), while its reusable rendering/utility libraries (`scenery`, `joist`, `dot`, `kite`, `phet-core`) are MIT. Check the license file of the specific repo you depend on.
- Sandboxels currently has no explicit OSI license grant on GitHub (`NOASSERTION`); treat it as "look but don't reuse" until the author clarifies terms.
- Star counts for cannon-es and PhET sub-repos were confirmed via web search rather than a live GitHub API call (rate-limited at verification time); treat as approximate.

## License Summary
| Repository | License |
|---|---|
| [Matter.js](https://github.com/liabru/matter-js) | MIT |
| [three.js](https://github.com/mrdoob/three.js) | MIT |
| [cannon-es](https://github.com/pmndrs/cannon-es) | MIT |
| [p5.js](https://github.com/processing/p5.js) | LGPL-2.1 |
| [PhET / scenery](https://github.com/phetsims/scenery) | MIT (libraries) / GPL-3.0 (sim source) |
| [Plotly.js](https://github.com/plotly/plotly.js) | MIT |
| [Sandboxels](https://github.com/R74nCom/sandboxels) | None / NOASSERTION (flagged) |
