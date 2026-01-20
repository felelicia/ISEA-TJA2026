Example Apache Access Log Line:

swift

CopyEdit

127.0.0.1 - - [29/Jun/2025:12:34:56 +0000] "GET /index.html HTTP/1.1" 200 1043


🔍 Bash Script with Regex for Parsing Apache Logs

bash

CopyEdit

#!/bin/bash


LOGFILE="/var/log/apache2/access.log"

REGEX='^([0-9]+\.[0-9]+\.[0-9]+\.[0-9]+) .* \[([^\]]+)\] "([A-Z]+) ([^ ]+) HTTP/[0-9.]+" ([0-9]{3}) ([0-9]+|-)'


echo "IP Address | Date/Time | Method | URL | Status | Bytes"

echo "--------------------------------------------------------------------------------"


while IFS= read -r line; do

if [[ $line =~ $REGEX ]]; then

ip="${BASH_REMATCH[1]}"

datetime="${BASH_REMATCH[2]}"

method="${BASH_REMATCH[3]}"

url="${BASH_REMATCH[4]}"

status="${BASH_REMATCH[5]}"

bytes="${BASH_REMATCH[6]}"


printf "%-14s | %-21s | %-6s | %-13s | %-6s | %-6s\n" \

"$ip" "$datetime" "$method" "$url" "$status" "$bytes"

fi

done < "$LOGFILE"


📘 Explanation of Regex:

Group Match Target Regex Expression

1 IP Address ([0-9]+\.[0-9]+\.[0-9]+\.[0-9]+)

2 Date/Time \[([^\]]+)\]

3 HTTP Method "([A-Z]+)

4 Requested URL ([^ ]+)

5 HTTP Status Code ([0-9]{3})

6 Bytes Transferred `([0-9]+


✅ Output (Sample):

pgsql

CopyEdit

IP Address | Date/Time | Method | URL | Status | Bytes

--------------------------------------------------------------------------------

127.0.0.1 | 29/Jun/2025:12:34:56 +0000 | GET | /index.html | 200 | 1043


🔹 1. Script to Extract Only Failed Requests (HTTP Status ≥ 400)

#!/bin/bash

LOGFILE="/var/log/apache2/access.log"

REGEX='^([0-9]+\.[0-9]+\.[0-9]+\.[0-9]+) .* \[([^\]]+)\] "([A-Z]+) ([^ ]+) HTTP/[0-9.]+" ([0-9]{3}) ([0-9]+|-)'

echo "FAILED REQUESTS:"

echo "IP Address | Date/Time | Method | URL | Status | Bytes"

echo "--------------------------------------------------------------------------------"

while IFS= read -r line; do

if [[ $line =~ $REGEX ]]; then

status="${BASH_REMATCH[5]}"

if (( status >= 400 )); then

ip="${BASH_REMATCH[1]}"

datetime="${BASH_REMATCH[2]}"

method="${BASH_REMATCH[3]}"

url="${BASH_REMATCH[4]}"

bytes="${BASH_REMATCH[6]}"

printf "%-14s | %-21s | %-6s | %-13s | %-6s | %-6s\n" \

"$ip" "$datetime" "$method" "$url" "$status" "$bytes"

fi

fi

done < "$LOGFILE"


🔹 2. Script to Output as CSV Format

#!/bin/bash

LOGFILE="/var/log/apache2/access.log"

REGEX='^([0-9]+\.[0-9]+\.[0-9]+\.[0-9]+) .* \[([^\]]+)\] "([A-Z]+) ([^ ]+) HTTP/[0-9.]+" ([0-9]{3}) ([0-9]+|-)'


echo "ip,date_time,method,url,status,bytes"

while IFS= read -r line; do

if [[ $line =~ $REGEX ]]; then

ip="${BASH_REMATCH[1]}"

datetime="${BASH_REMATCH[2]}"

method="${BASH_REMATCH[3]}"

url="${BASH_REMATCH[4]}"

status="${BASH_REMATCH[5]}"

bytes="${BASH_REMATCH[6]}"

echo "$ip,\"$datetime\",$method,$url,$status,$bytes"

fi

done < "$LOGFILE"


#!/bin/bash

LOGFILE="/var/log/apache2/access.log"

# Extended log format must include user-agent at the end

REGEX='^([0-9]+\.[0-9]+\.[0-9]+\.[0-9]+) .* \[([^\]]+)\] "([A-Z]+) ([^ ]+) HTTP/[0-9.]+" ([0-9]{3}) ([0-9]+|-) "([^"]*)" "([^"]*)"'


192.168.1.10 - - [10/Jan/2026:13:55:36 +0800] "GET /index.html HTTP/1.1" 200 1043 "https://example.com" "Mozilla/5.0"

Group Captures Example

1 Client IP address (IPv4) 192.168.1.10

(skip) .* → identity / user fields - -

2 Timestamp (inside []) 10/Jan/2026:13:55:36 +0800

3 HTTP method GET

4 Requested path / URI /index.html

(skip) HTTP version HTTP/1.1

5 HTTP status code 200

6 Response size (bytes or -) 1043

7 Referrer https://example.com

8 User-Agent Mozilla/5.0



echo "IP Address | Method | URL | Status | User-Agent"

echo "---------------------------------------------------------------------"

while IFS= read -r line; do

if [[ $line =~ $REGEX ]]; then

ip="${BASH_REMATCH[1]}"

method="${BASH_REMATCH[3]}"

url="${BASH_REMATCH[4]}"

status="${BASH_REMATCH[5]}"

useragent="${BASH_REMATCH[8]}"

printf "%-14s | %-6s | %-13s | %-6s | %s\n" \

"$ip" "$method" "$url" "$status" "$useragent"

fi

done < "$LOGFILE"


⚠️ For the user-agent script, ensure your Apache log format includes user-agent:

LogFormat "%h %l %u %t \"%r\" %>s %b \"%{Referer}i\" \"%{User-Agent}i\"" combined


Singapore NRIC

^[STFGM]\d{7}[A-Z]$

S8827228H


Core building blocks

· . any char (except newline)

· \d digit [0-9]

· \w word char [A-Za-z0-9_]

· \s whitespace

· \D \W \S = “not digit / not word / not whitespace”

· [abc] one of a,b,c

· [^abc] not a,b,c

· [a-z] range

· | OR

· (...) capture group

· (?:...) non-capture group

Anchors (position)

· ^ start of string/line

· $ end of string/line

· \b word boundary

· \B not a word boundary

Quantifiers (repeat)

· * 0 or more

· + 1 or more

· ? 0 or 1

· {n} exactly n

· {n,} at least n

· {n,m} between n and m

· *? +? ?? {n,m}? lazy versions (match as little as possible)

Common “ready-to-use” patterns

Email (basic)

\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}\b


IPv4 (strict 0–255)

\b(?:(?:25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)\.){3}(?:25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)\b


URL (simple)

https?://[^\s/$.?#].[^\s]*

Singapore NRIC format only (structure)

^[STFGM]\d{7}[A-Z]$


Dates (YYYY-MM-DD)

\b\d{4}-\d{2}-\d{2}\b


Time (HH:MM 24h)

\b(?:[01]\d|2[0-3]):[0-5]\d\b


Extract text inside quotes

"([^"]*)"


Lookarounds (advanced)

· (?=...) positive lookahead (must be followed by…)

· (?!...) negative lookahead

· (?<=...) positive lookbehind (must be preceded by…)

· (?<!...) negative lookbehind

Example: match cat only if followed by s

cat(?=s)


Greedy vs lazy

· Greedy: .* (grabs as much as it can)

· Lazy: .*? (grabs as little as it can)🔹 3. Script to Include User-Agent Parsing

grep

1) Show only 4xx + 5xx lines

grep -E '\" (4|5)[0-9]{2} ' access.log

2) Count status codes

grep -oE '\" [1-5][0-9]{2} ' access.log | sort | uniq -c | sort -nr

3) Top 20 IPs hitting your server

grep -oE '([0-9]{1,3}\.){3}[0-9]{1,3}' access.log | sort | uniq -c | sort -nr | head -20

4) Show requests for a specific path

grep -E '\"(GET|POST) /login' access.log

5) Case-insensitive search

grep -i 'error' app.log

---

sed

1) Mask IP addresses (basic)

sed -E 's/\b([0-9]{1,3}\.){3}[0-9]{1,3}\b/[IP]/g' access.log

2) Extract the request line (between quotes)

sed -nE 's/.*"([^"]+)".*/\1/p' access.log

3) Replace multiple spaces with one (cleanup)

sed -E 's/[[:space:]]+/ /g' app.log

4) Print only lines between two timestamps (rough example)

sed -n '/10\/Jan\/2026:10:00:00/,/10\/Jan\/2026:10:15:00/p' access.log

---

awk

1) Top status codes (Apache combined log: status is $9)

awk '{print $9}' access.log | sort | uniq -c | sort -nr

2) Top requested URLs (request path is inside quotes; often $7 is the path)

awk '{print $7}' access.log | sort | uniq -c | sort -nr | head

3) Count 404s per IP

awk '$9==404 {print $1}' access.log | sort | uniq -c | sort -nr | head

4) Find slow requests (if your log has request time as last field, e.g. $NF)

awk '$NF > 1.0 {print $0}' access.log

5) Summarise bytes sent (bytes is $10; skip “-”)

awk '$10 ~ /^[0-9]+$/ {sum+=$10} END {print "Total bytes:", sum}' access.log

6) Extract user-agent (last quoted string in combined log)

awk -F\" '{print $6}' access.log | head

---

find

1) Find all .log files under /var/log

find /var/log -type f -name "*.log"

2) Find logs modified in last 1 day

find /var/log -type f -name "*.log" -mtime -1

3) Search across many logs for “error”

find /var/log -type f -name "*.log" -print0 | xargs -0 grep -nH 'error'

4) Search for 500 errors across all access logs

find . -type f -name "*access*.log" -print0 | xargs -0 grep -nH -E '\" 500 '

5) Find large logs (>100MB)

find /var/log -type f -size +100M -ls

---

Common “combo” pipelines (real-world)

Top 20 IPs causing 404

grep -E '\" 404 ' access.log | awk '{print $1}' | sort | uniq -c | sort -nr | head -20

Top 20 IPs causing 401/403 (auth probing)

grep -E '\" (401|403) ' access.log | awk '{print $1}' | sort | uniq -c | sort -nr | head -20

Top endpoints returning 500

grep -E '\" 500 ' access.log | awk '{print $7}' | sort | uniq -c | sort -nr | head -20
