# Overall Validation Summary

| Metric | Score (%) |
|---|---:|
| Overall Validation Score | 90 |
| Accuracy Score | 100 |
| Efficiency Score | 90 |
| Completeness Score | 80 |
| Overall Status | PASS WITH WARNINGS |

# Completeness Assessment

| Severity | Area | Issue | Recommendation |
|---|---|---|---|
| Medium | Completeness | Source data, mapped data, and mapping result details were available and contained 2 records each; required validation inputs were sufficient to perform mapping validation. | No action required. |
| Medium | Completeness | All 2 source records had corresponding mapped records by record id (10003, 10004); no required source records were skipped and no required mapped records were missing. | No action required. |
| Medium | Completeness | Required mapped business fields validated in mapped output were populated for both records: Migration Date, FI Name, Entity ID, Switch, Old Platform, New Platform, Service, CS Location, Total Card Count, and Using OneCall IVR. | No action required. |
| Low | Completeness | Field `DMcarding Spreadsheet - Migration Wave MM/DD/YYYY` was present in mapped data for both records, but mapping result details indicate it was unmatched during template update. This does not affect mapping validation completeness because workbook/template population is out of scope, but it is a downstream handoff warning. | Align downstream template column naming with mapped field naming if this field is intended to populate a workbook column. |

# Accuracy Assessment

| Severity | Area | Issue | Recommendation |
|---|---|---|---|
| Low | Accuracy | Source-to-target record counts matched exactly: 2 source records and 2 mapped records. | No action required. |
| Low | Accuracy | Record 10003 values were accurate: Migration Date `2026-03-05`, FI Name `Pacific Financial Services`, Entity ID `503`, Total Card Count `15600`, and Using OneCall IVR `SMS, Mobile App` matched source values. | No action required. |
| Low | Accuracy | Record 10004 values were accurate: Migration Date `2026-04-20`, FI Name `Metro Bank`, Entity ID `504`, Total Card Count `6400`, and Using OneCall IVR `IVR, SMS, Mobile App` matched source values. | No action required. |
| Low | Accuracy | Assigned/default values were internally consistent across both records: Switch `BIS`, Old Platform `EFT Services`, New Platform `Payments Debit`, Service `Basic`, and CS Location `Offshore`. No evidence of unsupported or inconsistent assigned values was found in the mapped output. | If formal mapping rules exist for assigned values, retain them with the run artifact so this validation can be fully rule-traceable. |
| Low | Accuracy | No duplicate mapped records were found, and no unexpected business values were introduced for directly mapped fields. | No action required. |
| Medium | Accuracy | Explicit mapping rules were not separately provided in the validation inputs. Accuracy for directly mapped fields was validated against source data, and static assigned values were validated for internal consistency only, not against an external rule specification. | Provide the formal mapping rules/configuration with future runs to enable strict rule-by-rule validation of transformations, defaults, and assigned values. |

# Efficiency Assessment

| Severity | Area | Issue | Recommendation |
|---|---|---|---|
| Low | Efficiency | No duplicate mapped records were detected; mapping processed all records once. | No action required. |
| Low | Efficiency | Mapped output used a concise set of business fields without redundant repeated field groups. | No action required. |
| Medium | Efficiency | The mapped output includes `DMcarding Spreadsheet - Migration Wave MM/DD/YYYY` in addition to `Migration Date`, and downstream processing reported the former as unmatched. This indicates a potentially unnecessary mapping operation for downstream template population. | Remove or rename the unmatched field in the mapping layer unless it is required by a documented downstream consumer. |
| Medium | Efficiency | Lack of explicit mapping rules reduces validation efficiency and traceability because assigned/default values cannot be conclusively validated against rule metadata. | Supply structured mapping rules for each run to improve automated validation coverage and governance traceability. |