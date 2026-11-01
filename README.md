![Banner](banner.png)

# cdd-configdrift-AlertOnSchemaViolation
Validates a configuration file against a JSON schema and alerts if the configuration violates the schema. Uses the `jsonschema` library.

## Install
```
git clone https://github.com/ShadowGuard-AI/cdd-configdrift-alertonschemaviolation
cd cdd-configdrift-alertonschemaviolation
pip install -r requirements.txt
```

## Usage
```
python3 main.py [-f json|yaml] [-l LEVEL] CONFIG_FILE SCHEMA_FILE
```

## Parameters
- `CONFIG_FILE`: path to the configuration file (JSON or YAML).
- `SCHEMA_FILE`: path to the JSON schema file.
- `-h`: show help message and exit.
- `-f`, `--format`: format of the config file: `json` or `yaml`. Autodetects if omitted.
- `-l`, `--log-level`: logging level: `DEBUG`, `INFO`, `WARNING`, `ERROR`, or `CRITICAL`.

## Verified behavior
- A config with port 80 against a schema requiring a minimum of 1024 printed the validation error and exited 1.
- A config with port 8080 against the same schema printed "Configuration is valid." and exited 0.
- The same valid result was obtained with `-f json` given explicitly.
- A missing config file exits 1.

## License
MIT License, see LICENSE.
