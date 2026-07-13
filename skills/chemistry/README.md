# Chemistry Skills & Resources

Curated, mature open-source libraries for cheminformatics, molecular visualization (2D/3D), file-format conversion, and periodic-table/chemistry-education data. Use these when building molecule viewers, reaction/SMILES tooling, periodic-table UIs, or computational-chemistry pipelines.

## Best Repositories

### [RDKit](https://github.com/rdkit/rdkit)
- **Stars:** ~3,515 (as of 2026-07-13)
- **License:** BSD-3-Clause
- **Last updated:** actively maintained, commits as of 2026-07-13

The most widely used open-source cheminformatics toolkit (C++ core with Python bindings) for molecule parsing (SMILES/SDF/Mol), descriptor calculation, substructure search, and reaction handling. Best as the core engine for any serious cheminformatics or drug-discovery-adjacent application.

**Installation:**
```bash
pip install rdkit
```

**Usage example:**
```python
from rdkit import Chem
from rdkit.Chem import Draw

mol = Chem.MolFromSmiles("CC(=O)Oc1ccccc1C(=O)O")  # aspirin
Draw.MolToFile(mol, "aspirin.png")
print(Chem.MolToSmiles(mol))
```

### [RDKit.js](https://github.com/rdkit/rdkit-js)
- **Stars:** ~239 (as of 2026-07-13)
- **License:** BSD-3-Clause
- **Last updated:** actively maintained, commits as of 2026-07-13

The official WebAssembly build of RDKit for JavaScript/browser use — brings molecule parsing, 2D-coordinate generation, and SVG rendering to the web without a server. Best when you need RDKit's cheminformatics functionality directly client-side (e.g. an in-browser structure editor or SMILES validator).

**Installation:**
```bash
npm i @rdkit/rdkit
```

**Usage example:**
```html
<script src="https://unpkg.com/@rdkit/rdkit/dist/RDKit_minimal.js"></script>
<script>
  window.initRDKitModule().then(function (RDKit) {
    const mol = RDKit.get_mol("c1ccccc1O"); // phenol
    document.getElementById("mol").innerHTML = mol.get_svg();
  });
</script>
```

### [3Dmol.js](https://github.com/3dmol/3Dmol.js)
- **Stars:** ~992 (as of 2026-07-13)
- **License:** BSD-3-Clause
- **Last updated:** actively maintained, commits as of 2026-07-13

WebGL-accelerated JavaScript library for interactive 3D molecular visualization (proteins, small molecules) directly in the browser, incorporating code from GLmol and three.js. Best for 3D protein/molecule viewers driven by PDB IDs or uploaded structure files, with zero native/plugin dependencies.

**Installation:**
```html
<script src="https://3Dmol.org/build/3Dmol-min.js"></script>
```

**Usage example:**
```javascript
const viewer = $3Dmol.createViewer(document.getElementById("viewer"));
$3Dmol.download("pdb:1MO8", viewer, { multimodel: true, frames: true }, function () {
  viewer.setStyle({}, { cartoon: { color: "spectrum" } });
  viewer.render();
});
```

### [Kekule.js](https://github.com/partridgejiang/Kekule.js)
- **Stars:** ~278 (as of 2026-07-13)
- **License:** MIT
- **Last updated:** actively maintained, commits as of 2026-07-13

A JavaScript cheminformatics toolkit providing a full 2D/3D molecule editor, structure I/O (Mol/SMILES/CML), and spectrum-data widgets for the browser. Best for building an in-browser chemical structure editor/drawing tool (a JS analogue to ChemDraw) rather than just a viewer.

**Installation:**
```html
<link rel="stylesheet" href="kekule/themes/default/kekule.css" />
<script src="kekule/kekule.min.js"></script>
```

**Usage example:**
```javascript
const composer = new Kekule.Editor.Composer(document.getElementById('editor'));
composer.setDimension('600px', '400px');
composer.setChemObj(Kekule.IO.loadFormatData('CC(=O)Oc1ccccc1C(=O)O', 'smi'));
```

### [Open Babel](https://github.com/openbabel/openbabel)
- **Stars:** ~1,355 (as of 2026-07-13)
- **License:** GPL-2.0 (copyleft — see Notes)
- **Last updated:** actively maintained, commits as of 2026-07-13

A mature chemical toolbox for converting, analyzing, and searching molecular data across 100+ file formats (SDF, Mol2, PDB, SMILES, CIF, and more). Best as the "universal converter" when you need to translate between chemistry file formats or run substructure/fingerprint searches from the command line or Python.

**Installation:**
```bash
conda install -c conda-forge openbabel
```

**Usage example:**
```bash
obabel aspirin.smi -O aspirin.sdf --gen3d
```

### [PyMOL (open-source)](https://github.com/schrodinger/pymol-open-source)
- **Stars:** ~1,715 (as of 2026-07-13)
- **License:** Custom BSD-style "Python License" (permissive, but non-standard wording — see Notes)
- **Last updated:** actively maintained, commits as of 2026-07-13

The open-source foundation of the widely used PyMOL molecular visualization system for rendering and analyzing protein/small-molecule 3D structures with publication-quality ray-tracing. Best for high-quality static/animated molecular renders and structural biology workflows (as opposed to lightweight in-browser viewers like 3Dmol.js).

**Installation:**
```bash
conda install -c conda-forge pymol-open-source
```

**Usage example:**
```python
from pymol import cmd

cmd.load("1mo8.pdb")
cmd.show("cartoon")
cmd.spectrum("count", "rainbow")
cmd.png("structure.png", width=800, height=600, dpi=150, ray=1)
```

### [Avogadro Libraries](https://github.com/OpenChemistry/avogadrolibs)
- **Stars:** ~654 (as of 2026-07-13)
- **License:** BSD-3-Clause
- **Last updated:** actively maintained, commits as of 2026-07-13

C++ libraries providing 3D rendering, molecular editing, and analysis for computational chemistry, molecular modeling, and materials science, powering the Avogadro2 desktop application. Best when you need a desktop-grade molecular-editing/analysis engine (with Open Babel integration) rather than a browser widget.

**Installation:**
```bash
conda install -c conda-forge avogadrolibs
```

**Usage example:**
```cpp
#include <avogadro/core/molecule.h>
#include <avogadro/io/fileformatmanager.h>

Avogadro::Core::Molecule molecule;
Avogadro::Io::FileFormatManager::instance().readFile(molecule, "aspirin.mol");
```

### [periodic-table](https://github.com/andrejewski/periodic-table)
- **Stars:** ~157 (as of 2026-07-13)
- **License:** ISC
- **Last updated:** maintained (data-focused package; infrequent updates expected for a static dataset)

A lightweight JavaScript/JSON dataset of all periodic-table elements (name, symbol, atomic number/weight, category, etc.). Best as the data source powering a custom periodic-table UI or chemistry-education quiz app — pair it with your own SVG/grid rendering.

**Installation:**
```bash
npm install periodic-table
```

**Usage example:**
```javascript
const elements = require('periodic-table');
const oxygen = elements.find(e => e.symbol === 'O');
console.log(oxygen.name, oxygen.atomicWeight); // "Oxygen" 15.999
```

## Notes
- **Open Babel is GPL-2.0 (copyleft):** if you statically link or vendor its code into a distributed application, that application must also be released under a GPL-compatible license. Using it as an external CLI tool (calling `obabel` as a subprocess) avoids this obligation; embedding its library directly does not.
- **PyMOL open-source's "Python License"** is a permissive, BSD-style license but with non-standard wording (not a stock SPDX license); read the actual `LICENSE` file before redistributing PyMOL code in a commercial product.
- RDKit, RDKit.js, 3Dmol.js, and Avogadro Libraries are all BSD-3-Clause and freely usable, including commercially, with attribution.
- `periodic-table` has modest star count and is a thin data package rather than a full application — included because there is no single dominant, actively-maintained "periodic table UI" repository; it's the cleanest maintained data source to build on.
- Star counts for RDKit.js, 3Dmol.js, Kekule.js, Open Babel, PyMOL, Avogadro Libraries, and periodic-table were cross-checked via both the GitHub API and web search as of 2026-07-13.

## License Summary
| Repository | License |
|---|---|
| [RDKit](https://github.com/rdkit/rdkit) | BSD-3-Clause |
| [RDKit.js](https://github.com/rdkit/rdkit-js) | BSD-3-Clause |
| [3Dmol.js](https://github.com/3dmol/3Dmol.js) | BSD-3-Clause |
| [Kekule.js](https://github.com/partridgejiang/Kekule.js) | MIT |
| [Open Babel](https://github.com/openbabel/openbabel) | GPL-2.0 (copyleft, flagged) |
| [PyMOL (open-source)](https://github.com/schrodinger/pymol-open-source) | Custom "Python License" (BSD-style, flagged) |
| [Avogadro Libraries](https://github.com/OpenChemistry/avogadrolibs) | BSD-3-Clause |
| [periodic-table](https://github.com/andrejewski/periodic-table) | ISC |
