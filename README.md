# Validator Configuration for Peppol BIS

## This is project is in beta status.
## Use it at your own risk.

## Getting started

### Prerequisites

Required tools:
* curl
* unzip
* Java 1.8 or newer

As a prerequisite you need the KoSIT Validator to run it.

```shell
# download validator
curl -L "https://github.com/itplr-kosit/validator/releases/download/v1.4.1/validationtool-1.4.1.zip" --output validator.zip

# unzip the validator (ensure the target directory "bin" is empty before unzipping)
unzip validator.zip -d bin/
```

### Running the validator

```
java -jar bin/validationtool-1.4.1-java8-standalone.jar -s scenarios.xml -h CrossIndustryInvoice_100pD16B.xml
```

Validator 1.4.1 help:

```
usage: check-tool  -s <scenario-config-file> [OPTIONS] [FILE]...
 -?,--help                                 Displays this help
 -c,--check-assertions <assertions-file>   Check the result using defined
                                           assertions
 -D,--daemon                               Starts a daemon listing for
                                           validation requests
 -d,--debug                                Prints some more debug
                                           information
 -G,--disable-gui                          Disables the GUI of the daemon
                                           mode
 -H,--host <arg>                           The hostname / IP address to
                                           bind the daemon. Default is
                                           localhost
 -h,--html                                 Extract and save any html
                                           content within  result as a
                                           separate file
 -l,--log-level <arg>                      Enables a certain log level for
                                           debugging purposes
 -m,--memory-stats                         Prints some memory stats
 -o,--output-directory <arg>               Defines the out directory for
                                           results. Defaults to cwd
 -P,--port <arg>                           The port to bind the daemon.
                                           Default is 8080
 -p,--print                                Prints the check result to
                                           stdout
 -r,--repository <arg>                     Directory containing scenario
                                           content
    --report-postfix <arg>                 Postfix of the generated report
                                           name
    --report-prefix <arg>                  Prefix of the generated report
                                           name
 -s,--scenarios <arg>                      Location of scenarios.xml e.g.
 -T,--threads <arg>                        Number of threads processing
                                           validation requests
 -X,--debug-logging                        Enables full debug log. Alias
                                           for -l debug
```
