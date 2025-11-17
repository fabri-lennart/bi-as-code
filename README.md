# BI as Code

![BI as Code](https://evidence.dev/hero_image_final4.png)

Explore LinkedIn analytics using **Evidence.dev** to build dashboards entirely in code, version-controlled and reproducible.

---

## Using VS Code

1. Install the [Evidence VS Code Extension](https://marketplace.visualstudio.com/items?itemName=Evidence.evidence-vscode)  
2. Open Command Palette (`Ctrl/Cmd + Shift + P`) → `Evidence: New Evidence Project`  
3. Click **Start Evidence** in the bottom status bar. This installs dependencies, generates sources from CSVs, and opens the preview.  

```bash
# If using CLI directly:
npm install
npm run sources           # Generate all sources (CSV → SQL tables)
npm run dev -- --host 0.0.0.0  # Start development server
```

## Knowledge Applied

This project demonstrates:

### SQL Queries
- Data was transformed, aggregated, and queried using SQL to create meaningful insights from CSV sources.

### Data Visualization
- Build dashboards with:
  - **Treemaps** for categorical breakdowns
  - **Line charts** for trends over time
  - **Bar charts** for comparisons

### Version Control & Reproducibility
- CSV sources, queries, and dashboards are all version-controlled.  
- Makes analytics auditable and shareable across teams.

### Deploy & Share
- The app is deployed and publicly accessible here:  
  [BI as Code Dashboard](hhttps://bi-as-code.evidence.app/)
