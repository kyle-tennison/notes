---
status: 🔥 Ahead
status1: ⚠️ Behind
status2: ✅ On-Schedule
status3: ⚠️ Behind
status4: ✅ On-Schedule
status5: ✅ On-Schedule
status6: ✅ On-Schedule
status7: ⚠️ Behind
status8: ⚠️ Behind
---
# Morning Check


![|640x268](../media/Pasted%20image%2020241106071600.png)

---
## Checklist

- [x] Check Emails
	- [x] Personal
	- [x] Georgia Tech
	- [ ] PTC
- [x] Check Canvas, load [School Tasks](School%20Tasks.md)
	- [x] ME 3057: Experimental Methods
	- [x] ME 3345: Heat Transfer
	- [x] ME 3180: Machine Design
	- [x] ME 3017: System Dynamics
	- [x] Calendar
- [x] Anki (5 min) 
- [x] [Personal Tasks](Personal%20Tasks.md)
- [x] Google Calendar
- [x] Track Habits
- [x] **Done**

Check and modify the calendar. After checking **Done**, be sure to follow the plan you have set for the day. Don't make any changes unless absolutely necessary.

---

### Work Status

**ME 3057: Experimental Methods**
```meta-bind
INPUT[inlineSelect(
  option('🔥 Ahead'),
  option('✅ On-Schedule'),
  option('⚠️ Behind')
):status2]
```

**ME 3345: Heat Transfer**
```meta-bind
INPUT[inlineSelect(
  option('🔥 Ahead'),
  option('✅ On-Schedule'),
  option('⚠️ Behind')
):status3]
```

**ME 3180: Machine Design**
```meta-bind
INPUT[inlineSelect(
  option('🔥 Ahead'),
  option('✅ On-Schedule'),
  option('⚠️ Behind')
):status4]
```

**ME 3017: System Dynamics**
```meta-bind
INPUT[inlineSelect(
  option('🔥 Ahead'),
  option('✅ On-Schedule'),
  option('⚠️ Behind')
):status5]
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