# CSV-to-OpenImmo converter

[![License](https://poser.pugx.org/oliverklee/csv_to_openimmo/license.svg)](https://packagist.org/packages/oliverklee/csv_to_openimmo)

This TYPO3 extension provides a Scheduler task that reads zipped CSV files
(created using
[Wodis Sigma](https://www.aareon.de/Produkte.5772.html?tx_aareon_selector[category]=5774))
from a configured folder and writes zipped OpenImmo files to another configured
folder. The task will also copy all image files and PDF from the ZIPs.

## Data format

You can find the CSV column definitions in the
[CSV Reader source code file](Classes/Service/CsvReader.php).

The functional tests also include an
[example CSV file](Tests/Functional/Fixtures/CorrectCsv/objects.csv).

The task will also automatically convert from ISO-9959-1 to UTF-8.

This converter will automatically mark all converted objects as "for rent".
Hence, it will not be able to convert objects that are for sale.

## Installing the extension

If you install the extension manually (not from the TER and not using Composer),
please make sure to name the extension directory `csv_to_openimmo`, not
`ext-csv_to_openimmo`.

## Caveats

The following OpenImmo fields currently are not imported:

- "vermarktungsart" (will always be "MIETE_PACHT")
- other image types than JPEG
- the type of transfer ("uebertragung > umfang", will always be "VOLL")

## Sponsorship

Development has been sponsored by
[ART-KON-TOR Kommunikation GmbH](https://www.art-kon-tor.de/).
