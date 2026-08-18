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
| Info | Completeness | Required validation inputs were available: source data, mapped data, and mapped records for 2 source records. | No action required. |
| Info | Completeness | Source record count = 2 and mapped record count = 2; all source records have corresponding mapped records by id/client_id (10003, 10004). | No action required. |
| Info | Completeness | All required mapped business fields present in the mapped output for both records: Migration Date, FI Name, Entity ID, Switch, Old Platform, New Platform, Service, CS Location, Total Card Count, Using OneCall IVR. | No action required. |
| Info | Completeness | The field `DMcarding Spreadsheet - Migration Wave MM/DD/YYYY` appears in the mapped output and was populated for both records. | No action required. |
| Info | Completeness | No missing required records, no empty required mapped values, and no zero-record failure condition detected. | No action required. |

# Accuracy Assessment

| Severity | Area | Issue | Recommendation |
|---|---|---|---|
| Info | Accuracy | Record 10003: Migration Date correctly mapped from source `migration_date` = `2026-03-05` to target `Migration Date` = `2026-03-05`. | No action required. |
| Info | Accuracy | Record 10003: FI Name correctly mapped from source `financial_institution_name` = `Pacific Financial Services`. | No action required. |
| Info | Accuracy | Record 10003: Entity ID correctly mapped from source `entity_id` = `503`. | No action required. |
| Info | Accuracy | Record 10003: Total Card Count correctly mapped from source `cardcount` = `15600`. | No action required. |
| Info | Accuracy | Record 10003: Using OneCall IVR correctly mapped from source `vru_activation_options` = `SMS, Mobile App`. | No action required. |
| Info | Accuracy | Record 10003: Assigned values are internally consistent in mapped output: Switch=`BIS`, Old Platform=`EFT Services`, New Platform=`Payments Debit`, Service=`Basic`, CS Location=`Offshore`. No contradiction was found in supplied inputs. | If formal mapping rules are available, retain them with the validation package to explicitly evidence assigned/default value logic. |
| Info | Accuracy | Record 10003: `DMcarding Spreadsheet - Migration Wave MM/DD/YYYY` correctly carries the source migration date value `2026-03-05`. | No action required. |
| Info | Accuracy | Record 10004: Migration Date correctly mapped from source `migration_date` = `2026-04-20` to target `Migration Date` = `2026-04-20`. | No action required. |
| Info | Accuracy | Record 10004: FI Name correctly mapped from source `financial_institution_name` = `Metro Bank`. | No action required. |
| Info | Accuracy | Record 10004: Entity ID correctly mapped from source `entity_id` = `504`. | No action required. |
| Info | Accuracy | Record 10004: Total Card Count correctly mapped from source `cardcount` = `6400`. | No action required. |
| Info | Accuracy | Record 10004: Using OneCall IVR correctly mapped from source `vru_activation_options` = `IVR, SMS, Mobile App`. | No action required. |
| Info | Accuracy | Record 10004: Assigned values are internally consistent in mapped output: Switch=`BIS`, Old Platform=`EFT Services`, New Platform=`Payments Debit`, Service=`Basic`, CS Location=`Offshore`. No contradiction was found in supplied inputs. | If formal mapping rules are available, retain them with the validation package to explicitly evidence assigned/default value logic. |
| Info | Accuracy | Record 10004: `DMcarding Spreadsheet - Migration Wave MM/DD/YYYY` correctly carries the source migration date value `2026-04-20`. | No action required. |
| Warning | Accuracy | Explicit mapping rules were not supplied in the provided context. Direct source-to-target mappings were validated against source data, but assigned/default values and any potential transformation logic could only be validated for internal consistency, not against formal rule definitions. | Provide the mapping rules artifact used by the DI DM Mapper Agent in future runs to enable rule-by-rule validation of defaults, transformations, and conditional logic. |
| Info | Accuracy | No source-to-target mismatches, unsupported business values, incorrect transformations, or unexpected substituted values were detected in the supplied mapped output. | No action required. |

# Efficiency Assessment

| Severity | Area | Issue | Recommendation |
|---|---|---|---|
| Info | Efficiency | No duplicate mapped records were detected; mapped record ids are unique (10003, 10004). | No action required. |
| Warning | Efficiency | The updater details reported `DMcarding Spreadsheet - Migration Wave MM/DD/YYYY` as unmatched for both records, while the mapped output still contains populated values for that field. This indicates an inconsistency between mapping output and downstream updater processing metadata. | Review the mapping-to-updater field name alignment so processing metadata and mapped payload behavior are consistent. |
| Warning | Efficiency | The mapped output contains both `DMcarding Spreadsheet - Migration Wave MM/DD/YYYY` and `Migration Date`, each populated with the same value per record. If both are not required by mapping configuration, this may represent redundant mapping effort. | Confirm whether both fields are required. If not, remove the redundant target field from the mapping workflow. |
| Info | Efficiency | Record-level mapping behavior is consistent across both records for assigned fields and direct mappings. | No action required. |
| Info | Efficiency | No evidence of unnecessary duplicate records or inconsistent record processing was found in the supplied mapped output. | No action required. |