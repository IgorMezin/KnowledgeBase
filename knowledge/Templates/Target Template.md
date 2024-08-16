---
создал заметку: "{{date}}"
---

```dataviewjs
const totalTasks = dv.current().file.tasks.length;
const completedTasks = dv.current().file.tasks.filter(t => t.completed).length;
const progress = totalTasks > 0 ? (completedTasks / totalTasks) * 100 : 0;
dv.span(`progress: ${progress.toFixed(2)}%`);
```

**Примечание:**
- [ ] ffdd
