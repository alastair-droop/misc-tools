#Miscellaneous Bioinformatics Tools

This is a set of miscellaneous bioinformatics tools.

##cutadapt-stats

This script extracts cutadapt statistics from from a set of [cutadapt](https://cutadapt.readthedocs.io/en/stable/) log files and outputs the data in a tabular format.

###Usage

~~~bash
cutadapt-stats [-h] [-v] [-n] [-c] <filename> [<filename> ...]
~~~

positional arguments:

* `<filename>` cutadapt log file(s) to process

optional arguments:

* `-h`, `--help` show this help message and exit
* `-v`, `--version` show program's version number and exit
* `-n`, `--no-header` suppress column headers
* `-c`, `--csv` output data as CSV (ignores -n)

For each log file, either a single entry (if it was a single pair) or two
entries (if it was a pair) are returned. The output columns are:

* `id`        : The log file ID
* `file`      : The log file
* `type`      : The type
* `r_total`   : Total reads processed
* `b_total`   : Total bases processed
* `r_out`     : Total reads passing filter
* `b_out`     : Total bases passing filter
* `r_adapt`   : Number of reads with adapter contamination
* `r_rm_long` : Reads rejected as too long (flag -M)
* `r_rm_short`: Reads rejected as too short (flag -m
* `r_rm_other`: Reads rejected for any other reason
* `b_rm_adapt`: Bases trimmed as adapter
* `b_rm_qual` : Bases trimmed as low quality (flag -q)
* `b_rm_other`: Reads trimmed for any other reason

###Installation
The script should be executable on any system that has python3 installed. On python version <3.2, the [argparse](https://pypi.python.org/pypi/argparse) package is not included in the standard library and must be separately installed.


