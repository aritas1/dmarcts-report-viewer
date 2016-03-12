# dmarcts-report-viewer
A PHP viewer for DMARC records that have been parsed by [John Levine's rddmarc script](http://www.taugh.com/rddmarc/) or the [dmarcts-report-parser.pl](https://github.com/techsneeze/dmarcts-report-parser)
* Allow to view pass/fail data for the parsed reports
* Identify potential DMARC related issues through red/orange/green signals

## Installation and Configuration

NOTE: The viewer expects that you have already populated a database with data from [John Levine's rddmarc script](http://www.taugh.com/rddmarc/) or the [dmarcts-report-parser.pl](https://github.com/techsneeze/dmarcts-report-parser) script.

Download the required files:
```
git clone https://github.com/techsneeze/dmarcts-report-viewer.git
```

Once the php files ave been downloaded, you will need to copy `dmarcts-report-viewer-config.php.sample` to `dmarcts-report-viewer-config.php`.  

```
cp dmarcts-report-viewer-config.php.sample dmarcts-report-viewer-config.php
```

Next, edit these basic configuration options at the top of the `dmarcts-report-viewer-config.php` script with the appropriate information:

```
$dbhost="localhost";
$dbname="dmarc";
$dbuser="dmarc";
$dbpass="xxx";
```

Ensure that `dmarcts-report-viewer-config.php`, `dmarcts-report-viewer.php`, anf `default.css` are in the same folder.
## Usage

Navigate in your browser to the location of the `dmarcts-report-viewer.php` file.

You should be presented with the basic report view, allowing you to navigate through the reports that have been parsed.

### Legend of the Colors
* Green : DKIM and SPF = pass
* Red : DKIM and SPF = fail
* Orange : Either DKIM or SPF (but not both) = fail
* Yellow : Some other condition, and should be investigated (e.g. DKIM or SPF result were missing)


More info can currently be found at : [TechSneeze.com](http://www.techsneeze.com/dmarc-report/)
