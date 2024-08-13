# CVE-crawler

CVE-crawler is a terminal tool that has two modes: search and info. The `search` method can be used to search CVEs related to some specified keyword and display its most relevant information. First, the newest vulnerability is displayed and when "Enter" is pressed, the previous related is displayed in a infinite loop until the oldest vulnerability or until `ctrl+c` is pressed.

# Usage

## Install dependencies:

```bash
pip3 install -r requirements.txt
```

Run `python3 cve-crawler.py --help` to see the help panel:

```plaintext
❯ python3 cve-crawler.py --help
usage: cve-crawler [-h] [--keyword KEYWORD] [--cve CVE] {search,info}

CVE-crawler is a terminal tool that can be used to search vulnerabilities for a keyword and display its most relevant information or retrieve the relevant information of a specific
CVE id.

positional arguments:
  {search,info}      The method to retrieve info of CVEs: search (search CVEs by keyword), info (retrieve info of a CVE id)

options:
  -h, --help         show this help message and exit
  --keyword KEYWORD  Specify a keyword to search CVEs (separated by commas)
  --cve CVE          Specify a CVE to see info of it
```

## Search vulnerabilities related to a keyword

To search vulnerabilities related to a specified keyword:

```plaintext
python3 cve-crawler.py search --keyword 'laravel'
```

The result looks like this, and when enter is pressed, it goes to the next older vulnerability:

![search result](/screenshots/search-result.png)

## Retrieve info of a CVE id

To retrieve info of a CVE id, just specify the `info` method and the CVE id with --cve:

```plaintext
python3 cve-crawler.py info --cve 'CVE-2024-7495'
```

The result looks like this:

![CVEInfo result](/screenshots/CVEInfoResult.png)