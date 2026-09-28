---
status: 🔥 Ahead
status1: ⚠️ Behind
status2: ✅ On-Schedule
status3: ⚠️ Behind
status4: ✅ On-Schedule
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
	- [ ] Georgia Tech
- [ ] Check Canvas, load [School Tasks](School%20Tasks.md)
	- [ ] CP-2040
	- [ ] ME-4342
	- [ ] ME-3210
	- [ ] MGT-3078
	- [ ] ME-3058
- [ ] Anki (5 min) 
- [ ] [Personal Tasks](Personal%20Tasks.md)
- [ ] [Google Calendar](https://calendar.google.com/calendar/u/0/r)
- [ ] [Track Habits](https://openhabit.co)
- [ ] **Done**

Check and modify the calendar. After checking **Done**, be sure to follow the plan you have set for the day. Don't make any changes unless absolutely necessary.

---

### Work Status

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