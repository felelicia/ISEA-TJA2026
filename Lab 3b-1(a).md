What is a crontab file?

A crontab file is a schedule file used by cron (the Linux job scheduler) to run commands automatically at specific times or intervals.

Think of it as:

A timetable that tells Linux what to run and when to run it

---

What does “crontab” mean?

· cron → time-based job scheduler (from chronos, time)

· tab → table of scheduled jobs

So:

crontab = cron table

---

Where is the crontab file?

Each user has their own crontab, stored internally by the system.

You usually manage it with:

crontab -e # edit your crontab

crontab -l # list your crontab

System crontabs (advanced):

· /etc/crontab

· /etc/cron.d/

· /etc/cron.hourly/

· /etc/cron.daily/

---

Crontab file format (VERY IMPORTANT)

Each line = one scheduled job

* * * * * command-to-run

│ │ │ │ │

│ │ │ │ └── Day of week (0–7) (0 or 7 = Sunday)

│ │ │ └──── Month (1–12)

│ │ └────── Day of month (1–31)

│ └──────── Hour (0–23)

└────────── Minute (0–59)

---

Example: read this crontab line

0 2 * * * /usr/bin/backup.sh

Meaning:

· 0 → minute 0

· 2 → 2 AM

· * → every day of month

· * → every month

· * → every day of week

📌 Runs backup.sh every day at 2:00 AM

---

Common crontab patterns (students should know)

Pattern Meaning

* * * * * Every minute

0 * * * * Every hour

0 0 * * * Every day at midnight

Pattern Meaning

0 9 * * 1 Every Monday at 9 AM

*/5 * * * * Every 5 minutes

0 0 1 * * First day of every month

---

Special crontab shortcuts

These mean the same thing but are easier to read:

Shortcut Meaning

@reboot Run once at system startup

@hourly Every hour

@daily Once per day

@weekly Once per week

@monthly Once per month

Example:

@reboot /usr/bin/startup-script.sh

---

Crontab environment rules (IMPORTANT EXAM POINT)

Crontab:

· Does NOT load your shell profile

· Has a minimal PATH

· Needs full paths

❌ Bad:

backup.sh

✅ Correct:

/usr/bin/bash /home/ubuntu/backup.sh

---

Example: real crontab file

# Backup website every night

0 2 * * * /usr/bin/tar -czf /backup/site.tar.gz /var/www


# Clean temp files every Sunday

0 3 * * 0 /usr/bin/rm -rf /tmp/*

---

How cron logs jobs

Logs go to:

/var/log/syslog

Search:

grep CRON /var/log/syslog

---

Common student mistakes

Mistake Why it fails

Missing full path Cron cannot find command

Script not executable Permission denied

No output handling Errors invisible

Using ~ Not expanded in cron

---

Good practice (recommended)

Redirect output:

0 2 * * * /home/ubuntu/backup.sh >> /var/log/backup.log 2>&1
