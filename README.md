![Validate Scripts](https://github.com/Bryan-Gutierrez-IT/command-cards/actions/workflows/validate.yml/badge.svg)
# Command Cards

A Linux automation project that analyzes Bash command history and generates collectible-style command cards as a static web dashboard.

The system parses shell history, computes usage statistics using AWK, enriches commands with metadata from a CSV database, and generates styled HTML cards that can be viewed in a browser.

This project demonstrates practical Linux scripting, text processing, automation, and deployment workflows.
---

## Demo

![Command Cards Demo](docs/demo.png)

---

## Features

- Parses Bash command history  
- Calculates command statistics:
  - execution frequency  
  - argument density  
  - redirection usage  
- Ranks commands by usage  
- Enriches commands with rarity and flavor text from a CSV database  
- Generates styled HTML command cards from templates  
- Deploys the generated page to a web directory  

---

## Tech Stack

- Linux  
- Bash  
- AWK  
- sed  
- HTML / CSS  
- Apache-style web deployment  

---

## Project Structure

```
command-cards/
│
├── scripts/
│   ├── generate_cards.sh
│   ├── install.sh
│   ├── settings.sh
│   └── history_scrape.awk
│
├── templates/
│   ├── html/
│   └── style/
│
├── data/
│   ├── commands.csv
│   └── samples/
│       ├── sample_history.txt
│       └── generate_demo_history.sh
│
├── docs/
│   └── demo.png
│
├── build/      (generated output)
├── .gitignore
└── README.md
```

---

## How It Works

```
shell history
      │
      ▼
generate_cards.sh
      │
      ▼
history_scrape.awk
      │
      ├── command statistics
      ├── usage counts
      ▼
ranking + metadata enrichment
      │
      ▼
HTML template generation
      │
      ▼
cards.html
      │
      ▼
/var/www/html/cc/cards.html
```

---

## Installation

From the project root:

```bash
cd scripts
./install.sh
```

This installs the project to:

```
/opt/cc
```

and prepares the web directory:

```
/var/www/html/cc
```

---

## Generate Command Cards

Run the generator script:

```bash
cd /opt/cc/scripts
sudo ./generate_cards.sh
```

Or use the sample history file for demos:

```bash
sudo ./generate_cards.sh /opt/cc/data/samples/sample_history.txt
```

---

## View the Dashboard

Open the generated page in a browser:

```
http://localhost/cc/cards.html
```

or

```
http://<server-ip>/cc/cards.html
```

---

## Example Output

The dashboard displays command cards with:

- command name  
- rarity classification  
- execution count  
- argument density  
- redirection usage  
- mastery level  

Example commands shown in the dashboard:

```
apt upgrade
vim
grep
sed
gcc
rm
```

See `docs/demo.png` for a screenshot.

---

## Skills Demonstrated

- Linux automation  
- Shell scripting  
- AWK text processing  
- Static site generation  
- Data transformation pipelines  
- Deployment to a web directory  

---

## Future Improvements

- containerized deployment using Docker  
- CI checks for shell script linting  
- filtering commands by category  
- interactive command search  

---

## Author

Bryan Gutierrez  

Information Technology student focused on Linux systems, automation, and infrastructure.

---

## License

MIT License
