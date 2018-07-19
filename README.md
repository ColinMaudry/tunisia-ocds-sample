# Tunisia OCDS sample 1.0.1

Sample data for the development of Tunisia's open contracting API.

See the [OCDS documentation](http://standard.open-contracting.org/latest/en/) for more information.

## Field by field

The first column is the path to the data. The second column explains where the data comes from in [the source database structure](https://docs.google.com/spreadsheets/d/1vUfAmisUp4_Knbs33-SfVDPCX7nZZPd-8VVwI5cOX2c/edit).

| Header        |                                                                                  |
| ------------- | -------------------------------------------------------------------------------- |
| uri           | "urn:haicop:ocds:" for sample data, but the URL of the data when the API is live |
| version       | Always "1.1", until upgrade to a later version                                   |
| publisher     | Format to be defined (see issue #4)                                              |
| publishedDate | Date and time when the data was queried from the server                          |
| extensions    | Until upgrade, please keep the ones in the sample (enquiry and bids extensions). |

| releases       |                                                                       |
| -------------- | --------------------------------------------------------------------- |
| ocid           | Concatenation of OCID prefix and **Plan/planId**                      |
| id             | Concatenation of *ocid* and number (+1 on every change, see issue #1) |
| date           | YYYY-MM-DDThh:mm:ssZ (**Plan.date**)                                  |
| tag            | Always "tender"                                                       |
| initiationType | Always "tender"                                                       |

| releases.parties       |                                                    |
| ---------------------- | -------------------------------------------------- |
| name                   | Organizations/identifier                           |
| id                     | **Organizations/id**                               |
| identifier.scheme      | **Organizations/identifier_scheme** (see issue #3) |
| identifier.id          | **Organizations/identifier_id**                    |
| identifier.legalName   | **Organizations/identifier_legalName**             |
| address.streetAddress  | **Organizations/address_streetAdress**             |
| address.postalCode     | **Organizations/address_postalCode**               |
| address.locality       | **Organizations/address_locality**                 |
| address.region         | **Organizations/address_region**                   |
| address.countryName    | **Organizations/address_countryName**              |
| contactPoint.email     | **Organizations/contactPoint_email**               |
| contactPoint.faxNumber | **Organizations/contactPoint_faxNumber**           |
| contactPoint.name      | **Organizations/contactPoint_name**                |
| contactPoint.telephone | **Organizations/contactPoint_telephone**           |
| contactPoint.url       | **Organizations/contactPoint_url**                 |
| roles                  | See issue #2                                       |

| releases.buyer |                                                               |
| -------------- | ------------------------------------------------------------- |
| name           | The *parties.name* of the buyer for this contracting process. |
| id             | The *parties.id* of the buyer for this contracting process.   |


| releases.planning  |                           |
| ------------------ | ------------------------- |
| budget.description | **Budget/budgetSourceId** |
| budget.project     | **Plan/budgetYear**       |

| releases.tender                  |                                                        |
| -------------------------------- | ------------------------------------------------------ |
| id                               | **Tender/id**                                          |
| title                            | **Tender/title**                                       |
| status                           | **Tender/status**                                      |
| items.id                         | **Lot/id**                                             |
| items.description                | **Lot/description**                                    |
| items.classification.scheme      | Most likely it will always be "UNSPSC"                 |
| items.classification.id          | **Lot/classification_id**                              |
| items.classification.description | **Lot/classification_description**                     |
| items.quantity                   | **Lot/quantity**                                       |
| items.unit.id                    | **Lot/unit_id**                                        |
| items.unit.name                  | **Lot/unit_name**                                      |
| items.unit.scheme                | **Lot/unit_scheme**                                    |
| items.unit.uri                   | **Lot/unit_uri**                                       |
| items.value.amount               | **Lot/estimatedValueAmount**                           |
| items.value.currency             | **Lot/estimatedValueCurrency**                         |
| procurementMethod                | **Plan/ProcurementMethod**                             |
| mainProcurementCategory          | **Plan/procurementCategory**                           |
| awardCriteria                    | **Tender/awardCriteria**                               |
| awardCriteriaDetails             | **Tender/awardCriteriaDetails**                        |
| submissionMethod                 | **Tender/submissionMethod**                            |
| submissionMethodDetails          | **Tender/submissionMethodDetails**                     |
| tenderPeriod.startDate           | YYYY-MM-DDThh:mm:ssZ **Tender/tenderPeriod_startDate** |
| tenderPeriod.endDate             | YYYY-MM-DDThh:mm:ssZ **Tender/tenderPeriod_endDate**   |
| hasEnquiries                     | **Tender/hasEnquiries**                                |
| awardPeriod.startDate            | **Tender/awardPeriod_startDate**                       |
| awardPeriod.endDate              | **Tender/awardPeriod_endDate**                         |
| items.deliveryAddress.           | **Lot/deliveryAddress_**                               |
| tenderPeriod.startDate           | YYYY-MM-DDThh:mm:ssZ (**Plan/NoticePublicationDate**)  |
| tenderPeriod.endDate             | YYYY-MM-DDThh:mm:ssZ (**Plan/ResultPublicationDate**)  |
| documents                        | See table **Documents**                                |
| enquiries                        | See table **Enquiries**                                |

| releases.awards                  |                                                         |
| -------------------------------- | ------------------------------------------------------- |
| id                               | **Award/id**                                            |
| title                            | **Award/title**                                         |
| description                      | **Award/description**                                   |
| status                           | **Award/status**                                        |
| date                             | YYYY-MM-DDThh:mm:ssZ **Award/date**                     |
| value.amount                     | **Award/value_amount**                                  |
| value.currency                   | **Award/value_currency**                                |
| suppliers.id                     | **Award/supplierID**                                    |
| suppliers.name                   | **Award/supplierID**                                    |
| items.id                         | **Lot/id** (the one that matches **Award/LotID**)       |
| items.description                | **Lot/description**                                     |
| items.classification.scheme      | Most likely it will always be "UNSPSC"                  |
| items.classification.id          | **Lot/classification_id**                               |
| items.classification.description | **Lot/classification_description**                      |
| items.quantity                   | **Lot/quantity**                                        |
| items.unit.id                    | **Lot/unit_id**                                         |
| items.unit.name                  | **Lot/unit_name**                                       |
| items.unit.scheme                | **Lot/unit_scheme**                                     |
| items.unit.uri                   | **Lot/unit_uri**                                        |
| items.value.amount               | **Lot/estimatedValueAmount**                            |
| items.value.currency             | **Lot/estimatedValueCurrency**                          |
| contractPeriod.startDate         | YYYY-MM-DDThh:mm:ssZ **Award/contractPeriod_startDate** |
| contractPeriod.endDate           | YYYY-MM-DDThh:mm:ssZ **Award/contractPeriod_endDate**   |
| Documents                        | See table **Documents**                                 |

| releases.contracts |                                                    |
| ------------------ | -------------------------------------------------- |
| id                 | **Contract/id**                                    |
| awardID            | **Contract/awardID**                               |
| description        | **Contract/description**                           |
| status             | **Contract/status**                                |
| period.startDate   | YYYY-MM-DDThh:mm:ssZ **Contract/period_startDate** |
| period.endDate     | YYYY-MM-DDThh:mm:ssZ **Contract/period_endDate**   |
| documents          | See table **Documents**                            |
| dateSigned         | YYYY-MM-DDThh:mm:ssZ **Contract/dateSigned**       |
| value.amount       | **Contracts/value_amount**                         |
| value.currency     | **Contracts/value_currency**                       |
|                    |                                                    |

| releases.bids |                    |
| ------------- | ------------------ |
| bids.details  | See table **Bids** |

## Release notes

#### 1.0.1

- Fixed the role of the supplier in the parties block

### 1.0.0 (12/07/2018)

- Initial release
