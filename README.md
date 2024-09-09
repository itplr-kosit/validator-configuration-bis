# Validator Configuration for Peppol Billing BIS 3.0

This is a special configuration of the [KoSIT Validator](https://github.com/itplr-kosit/validator).

If you think you have found a bug, please [contact us](https://xeinkauf.de/peppol/).

Existing issues can be found at [our issue tracker](https://projekte.kosit.org/peppol/validator-configuration-bis/-/issues).

You can find packaged releases on [our GitLab project](https://projekte.kosit.org/peppol/validator-configuration-bis/-/releases).


This validator uses the latest Peppol BIS 2024-05 rules.

This is the "May 2024" release announced on 2024-05-27.

It is valid per 2024-08-27 00:00 CEST.

The next Peppol update is foreseen in November 2024.

**Please note: this configuration uses validation artefacts published by OpenPeppol ([OpenPeppol - GitHub](https://github.com/OpenPEPPOL)). Please use the [Peppol Service desk](https://openpeppol.atlassian.net/servicedesk/customer/portal/1) to report any issues related to the validation. KoSIT is offering this configuration of the [KoSIT Validator](https://github.com/itplr-kosit/validator), but excludes any liability.**

## Getting started

### Prerequisites

Required tools:
* curl
* unzip

As a prerequisite you need the KoSIT Validator to run it.

```shell
# download validator
curl -L "https://github.com/itplr-kosit/validator/releases/download/v1.5.0/validator-1.5.0-distribution.zip" --output validator.zip

# unzip the validator (ensure the target directory "bin" is empty before unzipping)
unzip validator.zip -d bin/
```

### Running the validator

Required tools:
* Java 11+

Verify all examples files (`test-files/good/*.xml`) and produced HTML output to directory `result-reports/` - all of them should be valid:

```shell
java -jar bin/validationtool-1.5.0-standalone.jar -s scenarios.xml -r "" -h -o result-reports/ test-files/good/ubl/*.xml
```

Note: eventually you need to explicitly use `"%JAVA_HOME%\bin\java"` on Windows

Validator 1.5.0 help:

```
Usage: KoSIT Validator [-?dX] [-l <logLevel>] [-r repository-path]... -s
                       scenario.xml [-s scenario.xml]... [[-D] [-H <host>] [-P
                       <port>] [-T <workerCount>] [-G]] [[-o <outputPath>] [-h]
                       [--serialize-report-input] [-c assertions-file]
                       [--report-postfix <reportPostfix>] [--report-prefix
                       <reportPrefix>] [-m] [-p] <files>...]
Structural and semantic validation of xml files
  -?, --help            display this help message
  -d, --debug           Prints some more debug information
  -l, --log-level <logLevel>
                        Enables a certain log level for debugging purposes
  -r, --repository repository-path
                        Directory containing scenario content
  -s, --scenarios scenario.xml
                        Location of scenarios.xml
  -X, --debug-logging   Enables full debug log. Alias for -l debug
Daemon options
  -D, --daemon          Starts a daemon listing for validation requests
  -G, --disable-gui     Disables the GUI of the daemon mode
  -H, --host <host>     The hostname / IP address to bind the daemon.
                          Default: localhost
  -P, --port <port>     The port to bind the daemon.
                          Default: 8080
  -T, --threads <workerCount>
                        Number of threads processing validation requests.
                          Default depends on processor count
CLI usage options
      <files>...        Files to validate
  -c, --check-assertions assertions-file
                        Check the result using defined assertions
  -h, --html, --extract-html
                        Extract and save any html content within result as a
                          separate file
  -m, --memory-stats    Prints some memory stats
  -o, --output-directory <outputPath>
                        Defines the out directory for results.
  -p, --print           Prints the check result to stdout
      --report-postfix <reportPostfix>
                        Postfix of the generated report name
      --report-prefix <reportPrefix>
                        Prefix of the generated report name
      --serialize-report-input
                        Serializes the report input to the cwd
```

## Building a release

Required tools:
* zip

```shell
zip -r -9 validation-configuration-bis-3.0.17.zip README.md scenarios.xml resources/*
```
