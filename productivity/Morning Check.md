---
status: 🔥 Ahead
status1: ⚠️ Behind
status2: ⚠️ Behind
status3: ✅ On-Schedule
status4: ⚠️ Behind
status5: ⚠️ Behind
status6: ⚠️ Behind
status7: ✅ On-Schedule
status8: ⚠️ Behind
---
# Morning Check


![|640x268](../media/Pasted%20image%2020241106071600.png)

---
## Checklist

- [ ] Check Emails
	- [x] Personal
	- [x] Georgia Tech
	- [ ] PTC
- [x] Check Canvas, load [School Tasks](School%20Tasks.md)
	- [x] COE 3001
	- [x] ME 2202
	- [x] ECE 3077
	- [x] Calendar
- [ ] Anki (5 min) 
- [ ] [Personal Tasks](Personal%20Tasks.md)
- [ ] Google Calendar
- [ ] [Daily Habits](https://app.dailyhabits.xyz)
- [ ] **Done**

Check and modify the calendar. After checking **Done**, be sure to follow the plan you have set for the day. Don't make any changes unless absolutely necessary.

---

### Work Status

**COE 3001** (Deformable Bodes)

```meta-bind
INPUT[inlineSelect(
  option('🔥 Ahead'),
  option('✅ On-Schedule'),
  option('⚠️ Behind')
):status1]
```

**COE 2001** (Dynamics)
```meta-bind
INPUT[inlineSelect(
  option('🔥 Ahead'),
  option('✅ On-Schedule'),
  option('⚠️ Behind')
):status2]
```

**ECE 3741** (Circuits Lab)
```meta-bind
INPUT[inlineSelect(
  option('🔥 Ahead'),
  option('✅ On-Schedule'),
  option('⚠️ Behind')
):status3]
```

**ME 3340** (Fluids)
```meta-bind
INPUT[inlineSelect(
  option('🔥 Ahead'),
  option('✅ On-Schedule'),
  option('⚠️ Behind')
):status4]
```

**ECE 3077** (Statistics)
```meta-bind
INPUT[inlineSelect(
  option('🔥 Ahead'),
  option('✅ On-Schedule'),
  option('⚠️ Behind')
):status5]
```

**Grading**
```meta-bind
INPUT[inlineSelect(
  option('🔥 Ahead'),
  option('✅ On-Schedule'),
  option('⚠️ Behind')
):status8]
```

**Research**
```meta-bind
INPUT[inlineSelect(
  option('🔥 Ahead'),
  option('✅ On-Schedule'),
  option('⚠️ Behind')
):status6]
```

**PTC**
```meta-bind
INPUT[inlineSelect(
  option('🔥 Ahead'),
  option('✅ On-Schedule'),
  option('⚠️ Behind')
):status7]
```


---

*Reset checks:*
```python
import re, pathlib, os
p=pathlib.Path("productivity/Morning Check.md")
t=p.read_text()
t=re.sub(r"Day:\s*(\d+)/(\d+)\s*\(\d+%?\)",lambda m:f"Day: {m[1]}/{m[2]} ({round(int(m[1])/int(m[2])*100)}%)",t)
t=re.sub(r"\[x\]","[ ]",t)
p.write_text(t)
```