# Week 2 — GroupBy, Merging, and Visualization

## Overview
In Week 2, you will build on your pandas foundations by learning how to:
- Group data using `groupby`
- Compute rate statistics (whiff %, swing %, putaway %)
- Merge tables to build more complex metrics
- Create visualizations (scatterplots, bar charts, heatmaps)
- Work with pitch–by–pitch Statcast-style data

This week is intentionally more open-ended than Week 1.
You're practicing *thinking like an analyst* — determining which operations you need,
in what order, and why.

---

## Learning Goals
- Understand how to aggregate data by categorical variables (pitch type, count, etc.)
- Practice deriving rate statistics from raw event data
- Learn to reshape data for visualizations (pivot tables, bins, heatmaps)
- Become comfortable with visualization fundamentals in Matplotlib and Seaborn
- Build confidence interpreting grouped data like an analyst

---

## Recommended Learning Resources
### FreeCodeCamp – Data Analysis With Python
Focus on:
- Pandas Conditional Selection
- Pandas DataFrames
- GroupBy and Aggregations
- Data Cleaning & Visualizations sections

### Matplotlib Basics
You only need:
- `plt.figure()`
- `plt.scatter()`
- `plt.bar()`
- `plt.hist()`
- Axes labels, titles, styles

### Seaborn (optional but helpful)
Useful functions:
- `sns.heatmap()`
- `sns.barplot()`
- `sns.lineplot()`

---

## Small Assignments

### **1. Pitch Type Summary Table**
Using your Statcast dataset, compute for each pitch type:
- **Swing %** = swings / total pitches  
- **Whiff %** = whiffs / swings  
- **Putaway %** = strikeouts on two-strike counts / two-strike pitches  

**Hints:**
- Identify swing/whiff events based on your dataset’s columns.
- Use `groupby("pitch_type")`.
- You may find it easier to compute intermediate tables and merge them together.

---

### **2. Count-Based Hitter Performance**
Group by count (0-0, 0-1, 1-2, …) and compute:
- Expected batting average (`estimated_ba_using_speedangle`)
- Mean exit velocity
- Mean launch angle
- Hard-hit %

**Hints:**
- If your dataset doesn't have a `count` column, build one from balls and strikes.
- Use `.agg()` to compute multiple statistics at once.

---

### **3. Heatmaps**
Make two heatmaps:

#### A. Whiff % by pitch location
- Bin vertical and horizontal pitch location using `pd.cut()`.
- Group by the two binned columns.
- Compute whiff %.
- Pivot into matrix form.
- Visualize with `sns.heatmap()`.

#### B. Hard-hit % by pitch type
- Either heatmap or bar chart is fine.
- A pivot table will help here.

---

## Folder Structure

Your repository should look like:

```
assignments/
  week2-viz/
    data/
    week2_notebook.ipynb
    README.md
```

---

## Deliverables
- A completed notebook (you show your reasoning, not just answers)
- At least two visualizations (scatterplot, heatmap, bar chart)
- A short written interpretation explaining key trends you found

---

## Tips for Success
- Write sections of your notebook in Markdown explaining your thinking.
- Keep your variable names descriptive.
- Validate your grouped results by manually checking small subsets.
- Try at least one plot styling option (grid, color maps, etc.).
- Don't fear trial and error — Week 2 is about exploration.

Good luck and have fun — this is your first “real” analytics toolkit week!
