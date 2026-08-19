# Overall Validation Summary

| Metric Score (%) | Value |
| --- | ---: |
| Overall Validation Score | 95% |
| Accuracy Score | 92% |
| Efficiency Score | 100% |
| Completeness Score | 100% |
| Overall Status | PASS WITH WARNINGS |

# Completeness Assessment

**No actionable findings identified.**

# Accuracy Assessment

| Severity | Area | Issue | Recommendation |
| --- | --- | --- | --- |
| Warning | Accuracy | The mapped output includes the field `DMcarding Spreadsheet - Migration Wave MM/DD/YYYY` with source date values, but the processing details state this field was unmatched during template update for both records. This indicates a source-to-mapped value was generated successfully but may not align with the downstream mapping configuration used by the template population step. | Reconcile the mapping configuration so that the generated mapped field names align consistently with the downstream template update configuration, or remove this field from the mapped output if it is not required. |

# Efficiency Assessment

**No actionable findings identified.**