![The blue string line close up, stretched along a brick course with one terracotta brick sitting proud of the line, the timber arch template soft behind](intro-banner.png)

# cdd-configdrift-alertonschemaviolation

![A rising brick arch on a building site under its tall timber arch template, a bricklayer checking the top course with a spirit level as the blue string line runs across the work](banner.png)

![A timber arch template frame drawn as a flat cut out emblem over a brick wall, a short course of terracotta bricks beneath it and a single blue string line stretched across the bricks, the heading plate](logo.png)

![Car and shaft scene in three bands: the indicator arrow creeping notch to notch, the lever taking single deliberate notches while the bell shakes once at a violation, string tags turning face in below](scene.svg)



# cdd-configdrift-AlertOnSchemaViolation
Validates a configuration file against a JSON schema and alerts if the configuration violates the schema. Uses the `jsonschema` library.

> Desk notice: the alert in this tool is a printed error and an exit code rather than any message sent elsewhere. Its own verified behavior section narrows the promise to a printed validation error and an exit code of 1, and no alert channel is named in any section.



![Claim ticket perforation divider](sep-heavy.svg)

## Install
```
git clone https://github.com/ShadowGuard-AI/cdd-configdrift-alertonschemaviolation
cd cdd-configdrift-alertonschemaviolation
pip install -r requirements.txt
```


![Claim ticket perforation divider](sep-light.svg)

## Usage
```
python3 main.py [-f json|yaml] [-l LEVEL] CONFIG_FILE SCHEMA_FILE
```


![Claim ticket perforation divider](sep-heavy.svg)

## Parameters
- `CONFIG_FILE`: path to the configuration file (JSON or YAML).
- `SCHEMA_FILE`: path to the JSON schema file.
- `-h`: show help message and exit.
- `-f`, `--format`: format of the config file: `json` or `yaml`. Autodetects if omitted.
- `-l`, `--log-level`: logging level: `DEBUG`, `INFO`, `WARNING`, `ERROR`, or `CRITICAL`.

> Desk notice: the log level arrives with no default stated in the README. The notch is left unpainted rather than guessed at.



![Claim ticket perforation divider](sep-heavy.svg)

## Verified behavior
- A config with port 80 against a schema requiring a minimum of 1024 printed the validation error and exited 1.
- A config with port 8080 against the same schema printed "Configuration is valid." and exited 0.
- The same valid result was obtained with `-f json` given explicitly.
- A missing config file exits 1.


![Claim ticket perforation divider](sep-heavy.svg)

## License
MIT License, see LICENSE.
