# Overall Validation Summary

| Metric | Score (%) |
|---|---:|
| Overall Validation Score | 95 |
| Accuracy Score | 100 |
| Efficiency Score | 85 |
| Completeness Score | 100 |
| Overall Status | PASS WITH WARNINGS |

# Completeness Assessment

| Severity | Area | Issue | Recommendation |
|---|---|---|---|
| Info | Completeness | Required validation inputs were available: source data present with 2 records; mapped data present with 2 records. | No action required. |
| Info | Completeness | Record coverage is complete: 2 source records were represented by 2 mapped records with matching record identifiers (10003, 10004). | No action required. |
| Info | Completeness | All mapped business fields present in the mapped output were populated for both records: Migration Date, FI Name, Entity ID, Switch, Old Platform, New Platform, Service, CS Location, Total Card Count, Using OneCall IVR. | No action required. |
| Info | Completeness | Field "DMcarding Spreadsheet - Migration Wave MM/DD/YYYY" was present in mapped output for both records. Because no mapping rules were supplied to establish whether this field is required, it was not treated as a required-field obligation. | Provide explicit mapping rules if this field must be governed as required. |
| Warning | Completeness | Mapping rules were not supplied. Validation was performed using source-to-target direct comparison for directly mapped fields and informational review of constant/assigned fields present in mapped output. | Supply explicit mapping rules to enable strict validation of required-field scope, transformations, defaults, and intentional exclusions. |

# Accuracy Assessment

| Severity | Area | Issue | Recommendation |
|---|---|---|---|
| Info | Accuracy | Record 10003: Migration Date matched source value 2026-03-05. | No action required. |
| Info | Accuracy | Record 10003: FI Name matched source financial_institution_name value Pacific Financial Services. | No action required. |
| Info | Accuracy | Record 10003: Entity ID matched source entity_id value 503. | No action required. |
| Info | Accuracy | Record 10003: Total Card Count matched source cardcount value 15600. | No action required. |
| Info | Accuracy | Record 10003: Using OneCall IVR matched source vru_activation_options value SMS, Mobile App. | No action required. |
| Info | Accuracy | Record 10003: Field "DMcarding Spreadsheet - Migration Wave MM/DD/YYYY" matched source migration_date value 2026-03-05. | No action required. |
| Info | Accuracy | Record 10004: Migration Date matched source value 2026-04-20. | No action required. |
| Info | Accuracy | Record 10004: FI Name matched source financial_institution_name value Metro Bank. | No action required. |
| Info | Accuracy | Record 10004: Entity ID matched source entity_id value 504. | No action required. |
| Info | Accuracy | Record 10004: Total Card Count matched source cardcount value 6400. | No action required. |
| Info | Accuracy | Record 10004: Using OneCall IVR matched source vru_activation_options value IVR, SMS, Mobile App. | No action required. |
| Info | Accuracy | Record 10004: Field "DMcarding Spreadsheet - Migration Wave MM/DD/YYYY" matched source migration_date value 2026-04-20. | No action required. |
| Warning | Accuracy | Assigned/default-style fields Switch=BIS, Old Platform=EFT Services, New Platform=Payments Debit, Service=Basic, and CS Location=Offshore were consistently populated across both records, but no mapping rules were supplied to prove these values are the expected configured assignments. | Provide explicit mapping rules so assigned/default values can be strictly validated instead of assessed only as consistent mapped values. |
| Warning | Accuracy | No formal transformation rules were supplied. Date values were validated as direct copies from source, not against any required formatting or transformation expectation. | Supply transformation rules if dates or other fields must be reformatted, normalized, or conditionally derived. |
| Warning | Accuracy | No unexpected-value failures were found in directly mapped fields, but unsupported-business-value detection for assigned/default fields is limited without mapping rules. | Provide lookup/default/conditional rules to enable strict unsupported-value validation. |

# Efficiency Assessment

| Severity | Area | Issue | Recommendation |
|---|---|---|---|
| Info | Efficiency | No duplicate mapped records were detected. Each source record ID had exactly one corresponding mapped record. | No action required. |
| Info | Efficiency | Mapping behavior was structurally consistent across both records for the set of mapped business fields. | No action required. |
| Warning | Efficiency | The mapped output includes both "DMcarding Spreadsheet - Migration Wave MM/DD/YYYY" and "Migration Date" with the same source value for each record. Without mapping rules, this appears potentially redundant. | Confirm whether both target fields are required; remove one mapping if duplicate population is unnecessary. |
| Warning | Efficiency | Efficiency validation could not assess unnecessary transformations, redundant logic, or intentionally duplicated target fields with full confidence because mapping rules were not supplied. | Provide explicit mapping rules and field intent to support stricter efficiency analysis. |