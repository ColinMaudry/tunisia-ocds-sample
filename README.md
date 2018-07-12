# Tunisia OCDS sample

Sample data for the development of Tunisia's open contracting API.

See the [OCDS documentation](http://standard.open-contracting.org/latest/en/) for more information.

## Field by field

| Path                                    | Documentation                                                   |
| --------------------------------------- | --------------------------------------------------------------- |
| ocid                                    | Concatenation of OCID prefix and **Plan/planId**                |
| id                                      | Concatenation of *ocid* and number (+1 on every change, see #1) |
| date                                    | YYYY-MM-DDThh:mm:ssZ (**Plan.date**)                            |
| tag                                     | Empty                                                           |
| initiationType                          | Always "tender"                                                 |
| parties.name                            | Organizations/identifier                                        |
| parties.id                              | **Organizations/id**                                            |
| parties.identifier.scheme               | **Organizations/identifier_scheme** (see #3)                    |
| parties.identifier.id                   | **Organizations/identifier_id**                                 |
| parties.identifier.legalName            | **Organizations/identifier_legalName**                          |
| parties.address.streetAddress           | **Organizations/address_streetAdress**                          |
| parties.address.postalCode              | **Organizations/address_postalCode**                            |
| parties.address.locality                | **Organizations/address_locality**                              |
| parties.address.region                  | **Organizations/address_region**                                |
| parties.address.countryName             | **Organizations/address_countryName**                           |
| parties.contactPoint.email              | **Organizations/contactPoint_email**                            |
| parties.contactPoint.faxNumber          | **Organizations/contactPoint_faxNumber**                        |
| parties.contactPoint.name               | **Organizations/contactPoint_name**                             |
| parties.contactPoint.telephone          | **Organizations/contactPoint_telephone**                        |
| parties.contactPoint.url                | **Organizations/contactPoint_url**                              |
| parties.roles                           | See #2                                                          |
| buyer.name                              | The *parties.name* of the buyer for this contracting process.   |
| buyer.id                                | The *parties.id* of the buyer for this contracting process.     |
| planning.budget.description             | **Budget/budgetSourceId**                                       |
| planning.budget.project                 | **Plan/budgetYear**                                             |
| tender.id                               | **Tender/id**                                                   |
| tender.title                            | **Tender/title**                                                |
| tender.status                           | **Tender/status**                                               |
| tender.items.id                         | **Lot/id**                                                      |
| tender.items.description                | **Lot/description**                                             |
| tender.items.classification.scheme      | Most likely it will always be "UNSPSC"                          |
| tender.items.classification.id          | **Lot/classification_id**                                       |
| tender.items.classification.description | **Lot/classification_description**                              |
| tender.items.quantity                   | **Lot/quantity**                                                |
| tender.items.unit.id                    | **Lot/unit_id**                                                 |
| tender.items.unit.name                  | **Lot/unit_name**                                               |
| tender.items.unit.scheme                | **Lot/unit_scheme**                                             |
| tender.items.unit.uri                   | **Lot/unit_uri**                                                |
| tender.items.value.amount               | **Lot/estimatedValueAmount**                                    |
| tender.items.value.currency             | **Lot/estimatedValueCurrency**                                  |
| tender.procurementMethod                | **Plan/ProcurementMethod**                                      |
| tender.mainProcurementCategory          | **Plan/procurementCategory**                                    |
| tender.awardCriteria                    | **Tender/awardCriteria**                                        |
| tender.awardCriteriaDetails             | **Tender/awardCriteriaDetails**                                 |
| tender.submissionMethod                 | **Tender/submissionMethod**                                     |
| tender.submissionMethodDetails          | **Tender/submissionMethodDetails**                              |
| tender.tenderPeriod.startDate           | **Tender/tenderPeriod_startDate**                               |
| tender.tenderPeriod.endDate             | **Tender/tenderPeriod_endDate**                                 |
| tender.hasEnquiries                     | **Tender/hasEnquiries**                                         |
| tender.awardPeriod.startDate            | **Tender/awardPeriod_startDate**                                |
| tender.awardPeriod.endDate              | **Tender/awardPeriod_endDate**                                  |
|                                         |                                                                 |



| tender.items.deliveryAddress. | **Lot/deliveryAddress_** (same value for all items in the release) |
| ----------------------------- | ------------------------------------------------------------------ |
| tender.tenderPeriod.startDate | YYYY-MM-DDThh:mm:ssZ (**Plan/NoticePublicationDate**)              |
| tender.tenderPeriod.endDate   | YYYY-MM-DDThh:mm:ssZ (**Plan/ResultPublicationDate**)              |
| tender.documents              | See table **Documents**                                            |
|                               |                                                                    |
