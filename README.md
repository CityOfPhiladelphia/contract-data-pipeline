# Contract Data Pipeline
Documentation for processing contract data to get it into www.phila.gov/contracts/data

Includes *Professional Services* and *Commodities* contracts.

## Professional Services Contracts
The Finance Department will send an email to the OIT data office each quarter with
an excel document (`.xlsx`) containing the most recent quarter's worth of data. This
excel document is provided by the contract system's vendor and cannot be automated
because the Mayor's Office must sign off on the data each quarter before it is
published.

1. Open the document in MS Excel or Google Sheets.
2. There will be two columns with odd names, ie `compute_0004` and `compute_006`.
Rename these to `vendor` and `short_desc`.
3. Set the `amt` and `tot_payments` fields to be numeric to strip out the spaces
and hyphens. It's okay for them to still contain commas and periods.
4. Save the file as `FY-20XX-QX.csv`, specifying the fiscal year and quarter in the
file name.
5. Drag & drop the file into the contracts repository's
[`professional-services/data` folder](https://github.com/CityOfPhiladelphia/contracts/tree/gh-pages/professional-services/data)
6. Open the new file in the repository and click the `Raw` button to get the 
downloadable URL
7. Put that downloadable URL into a new version/subset in the metadata catalog and
as a new resource in OpenDataPhilly

### Updating the website
Once the file is uploaded to the contracts repository, you need to tell the contracts
data website to use it.

1. Go to [professional-services/index.md](https://github.com/CityOfPhiladelphia/contracts/blob/gh-pages/professional-services/index.md)
and click the `Edit` button.
2. Update the year and quarter in the 5 places it is mentioned, following
[this example](https://github.com/CityOfPhiladelphia/contracts/commit/d5f63fd60610e8cb2a0d4708f4aecc3ac8a4882a)
3. Commit the file and verify it worked by visiting the
[contracts data website](http://www.phila.gov/contracts/data)
