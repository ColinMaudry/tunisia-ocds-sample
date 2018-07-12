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
| tender.tenderPeriod.startDate           | YYYY-MM-DDThh:mm:ssZ **Tender/tenderPeriod_startDate**          |
| tender.tenderPeriod.endDate             | YYYY-MM-DDThh:mm:ssZ **Tender/tenderPeriod_endDate**            |
| tender.hasEnquiries                     | **Tender/hasEnquiries**                                         |
| tender.awardPeriod.startDate            | **Tender/awardPeriod_startDate**                                |
| tender.awardPeriod.endDate              | **Tender/awardPeriod_endDate**                                  |
| tender.items.deliveryAddress.           | **Lot/deliveryAddress_**                                        |
| tender.tenderPeriod.startDate           | YYYY-MM-DDThh:mm:ssZ (**Plan/NoticePublicationDate**)           |
| tender.tenderPeriod.endDate             | YYYY-MM-DDThh:mm:ssZ (**Plan/ResultPublicationDate**)           |
| tender.documents                        | See table **Documents**                                         |
| award.id                                | **Award/id**                                                    |
| award.title                             | **Award/title**                                                 |
| award.description                       | **Award/description**                                           |
| award.status                            | **Award/status**                                                |
| award.date                              | YYYY-MM-DDThh:mm:ssZ **Award/date**                             |
| award.value.amount                      | **Award/value_amount**                                          |
| award.value.currency                    | **Award/value_currency**                                        |
| award.suppliers.id                      | **Award/supplierID**                                            |
| award.suppliers.name                    | **Award/supplierID**                                            |
| award.items.id                          | **Lot/id** (the one that matches **Award/LotID**)              |
| award.items.description                 | **Lot/description**                                             |
| award.items.classification.scheme       | Most likely it will always be "UNSPSC"                          |
| award.items.classification.id           | **Lot/classification_id**                                       |
| award.items.classification.description  | **Lot/classification_description**                              |
| award.items.quantity                    | **Lot/quantity**                                                |
| award.items.unit.id                     | **Lot/unit_id**                                                 |
| award.items.unit.name                   | **Lot/unit_name**                                               |
| award.items.unit.scheme                 | **Lot/unit_scheme**                                             |
| award.items.unit.uri                    | **Lot/unit_uri**                                                |
| award.items.value.amount                | **Lot/estimatedValueAmount**                                    |
| award.items.value.currency              | **Lot/estimatedValueCurrency**                                  |
| award.contractPeriod.startDate          | YYYY-MM-DDThh:mm:ssZ **Award/contractPeriod_startDate**         |
| award.contractPeriod.endDate            | YYYY-MM-DDThh:mm:ssZ **Award/contractPeriod_endDate**           |
| award.Documents                         | See table **Documents**                                         |
| contract.id                             | **Contract/id**                                                 |
| contract.awardID                        | **Contract/awardID**                                            |
| contract.description                    | **Contract/description**                                        |
| contract.status                         | **Contract/status**                                             |
| contract.period.startDate               | YYYY-MM-DDThh:mm:ssZ **Contract/period_startDate**              |
| contract.period.endDate                 | YYYY-MM-DDThh:mm:ssZ **Contract/period_endDate**                |
| contract.documents                      | See table **Documents**                                         |
|                                         |                                                                 |
