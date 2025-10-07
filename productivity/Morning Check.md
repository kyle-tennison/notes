# Morning Check
For daily activities

![](../media/Pasted%20image%2020241106071600.png)

## Checklist

- [x] Check Emails
	- [x] Personal
	- [x] Georgia Tech
	- [x] PTC
- [x] Check Canvas, load [School Tasks](School%20Tasks.md)
	- [x] Calendar
- [x] Anki (5 min) 
- [x] Vocab Mountain
	- Day: 7/34 (21%)
- [x] [Personal Tasks](Personal%20Tasks.md)
- [x] Google Calendar
- [x] [Daily Habits](https://app.dailyhabits.xyz)
- [x] **Done**

Check and modify the calendar. After checking **Done**, be sure to follow the plan you have set for the day. Don't make any changes unless absolutely necessary.

*Reset checks:*
```python
import re, pathlib, os
p=pathlib.Path("productivity/Morning Check.md")
t=p.read_text()
t=re.sub(r"Day:\s*(\d+)/(\d+)\s*\(\d+%?\)",lambda m:f"Day: {m[1]}/{m[2]} ({round(int(m[1])/int(m[2])*100)}%)",t)
t=re.sub(r"\[x\]","[ ]",t)
p.write_text(t)
```