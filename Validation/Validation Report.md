# Overall Validation Summary

| Metric | Score (%) |
|---|---:|
| Overall Validation Score | 97 |
| Accuracy Score | 100 |
| Efficiency Score | 90 |
| Completeness Score | 100 |
| Overall Status | PASS WITH WARNINGS |

# Completeness Assessment

| Severity | Area | Issue | Recommendation |
|---|---|---|---|
| Info | Completeness | Required validation inputs were available: source data present with 2 records, mapped data present with 2 records, and mapped output contained records. | No action required. |
| Info | Completeness | Record coverage is complete: 2 source records were represented by 2 mapped records, and no required source records were missing. | No action required. |
| Info | Completeness | Required mapped business fields validated in the mapped output for both records: Migration Date, FI Name, Entity ID, Switch, Old Platform, New Platform, Service, CS Location, Total Card Count, and Using OneCall IVR. | No action required. |
| Info | Completeness | The field `DMcarding Spreadsheet - Migration Wave MM/DD/YYYY` exists in the mapped data but was reported as unmatched by the downstream template updater. This is outside scope for mapping completeness because workbook/template matching is not validated here. | No action required in mapping validation; review downstream template mapping separately if needed. |

# Accuracy Assessment

| Severity | Area | Issue | Recommendation |
|---|---|---|---|
| Info | Accuracy | Record 10003 passed source-to-target validation. Expected values matched actual mapped values for Migration Date (`2026-03-05`), FI Name (`Pacific Financial Services`), Entity ID (`503`), Total Card Count (`15600`), and Using OneCall IVR (`SMS, Mobile App`). Assigned values were consistently populated as Switch=`BIS`, Old Platform=`EFT Services`, New Platform=`Payments Debit`, Service=`Basic`, and CS Location=`Offshore`. | No action required. |
| Info | Accuracy | Record 10004 passed source-to-target validation. Expected values matched actual mapped values for Migration Date (`2026-04-20`), FI Name (`Metro Bank`), Entity ID (`504`), Total Card Count (`6400`), and Using OneCall IVR (`IVR, SMS, Mobile App`). Assigned values were consistently populated as Switch=`BIS`, Old Platform=`EFT Services`, New Platform=`Payments Debit`, Service=`Basic`, and CS Location=`Offshore`. | No action required. |
| Info | Accuracy | No source-to-target mismatches were identified for directly mapped fields. No unsupported business values were introduced in Entity ID, FI Name, Migration Date, Total Card Count, or Using OneCall IVR. | No action required. |
| Info | Accuracy | No transformation errors were detected. The mapped dates remained in source format (`YYYY-MM-DD`), which is acceptable because no rule requiring date transformation was supplied. | No action required unless a date-format transformation rule exists and should be added to mapping rules. |
| Warning | Accuracy | Mapping rules were not explicitly provided in the validation input. Validation was completed using observable source-to-target behavior and mapped assigned/default values present in all records, but rule-level certainty for assigned fields could not be independently verified from a formal rule set. | Provide the formal mapping rules in future runs to enable explicit rule-by-rule validation of assigned/default and transformed values. |

# Efficiency Assessment

| Severity | Area | Issue | Recommendation |
|---|---|---|---|
| Info | Efficiency | No duplicate mapped records were found. Source record IDs `10003` and `10004` each map to exactly one output record. | No action required. |
| Info | Efficiency | Mapped field population is consistent across both records, indicating stable mapping behavior for the validated business fields. | No action required. |
| Warning | Efficiency | An extra mapped field, `DMcarding Spreadsheet - Migration Wave MM/DD/YYYY`, was generated for both records and later reported as unmatched by the downstream template updater. This is not a mapping accuracy/completeness failure, but it indicates an unnecessary field mapping relative to the downstream write process. | Remove the redundant field from mapped output or align downstream configuration if the field is intentionally required elsewhere. |