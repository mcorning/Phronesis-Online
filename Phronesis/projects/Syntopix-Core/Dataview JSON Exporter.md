```dataviewjs
let pages = dv.pages().where(p => p.type === "topiq");
let nodes = pages.map(p => ({
  data: {
    id: p.file.name,
    label: p.title,
    fitness: p.summary ?? "no summary"
  }
}));

let edges = pages.flatMap(p =>
  (p.topiqx ?? []).map(target => ({
    data: {
      source: p.file.name,
      target: "Topiq-" + target,
      label: "refines"
    }
  }))
);

dv.paragraph("```json\n" + JSON.stringify([...nodes, ...edges], null, 2) + "\n```");
```


- This **renders a JSON block inside your note**
- You can then copy that directly to `elements.json`

---

### ✅ 3. **Use Obsidian Advanced URI Plugin (Optional)**
- Lets you trigger Dataview views from external scripts
- Or dynamically pull from `.md` → `csv` pipeline

(This is overkill unless you're automating at scale.)

---

Would you like me to prep that inline DataviewJS block inside your vault to get a working `elements.json`?
