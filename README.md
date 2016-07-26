# Miscellaneous Bioinformatics Tools

This is a set of miscellaneous bioinformatics tools.

## cutadapt-stats

This script extracts cutadapt statistics from from a set of [cutadapt](https://cutadapt.readthedocs.io/en/stable/) log files and outputs the data in a tabular format.

### Usage

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

### Installation

The script should be executable on any system that has python3 installed. On python version <3.2, the [argparse](https://pypi.python.org/pypi/argparse) package is not included in the standard library and must be separately installed.

## fastqc-extract

This script processes a set of [FastQC](http://www.bioinformatics.bbsrc.ac.uk/projects/fastqc/) ZIP files to produce summary tables.

### Usage

~~~bash
fastqc-extract [-h] [-v] [-c] [-e] [-s] <module> <filename> [<filename> ...]
~~~

positional arguments:

* `<module>` The module
* `<filename>` FastQC ZIP file(s) to process

optional arguments:

* `-h`, `--help` show this help message and exit
* `-v`, `--version` show program's version number and exit
* `-c`, `--csv` return CSV-formatted data
* `-e`, `--header` include header in output
* `-s`, `--summary` generate module summary

### Modules

Modules can be provided by name or by number. Non-standard modules must be supplied by name:

|Number|Name                        |
|-----:|:---------------------------|
|     1|Basic Statistics            |
|     2|Per base sequence quality   |
|     3|Per tile sequence quality   |
|     4|Per sequence quality scores |
|     5|Per base sequence content   |
|     6|Per sequence GC content     |
|     7|Per base N content          |
|     8|Sequence Length Distribution|
|     9|Sequence Duplication Levels |
|    10|Overrepresented sequences   |
|    11|Adapter Content             |
|    12|Kmer Content                |

### Installation

The script should be executable on any system that has python3 installed. On python version <3.2, the [argparse](https://pypi.python.org/pypi/argparse) package is not included in the standard library and must be separately installed.
