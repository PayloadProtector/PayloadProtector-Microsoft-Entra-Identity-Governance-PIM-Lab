# GRC Security Control Assessment — Identity Governance and PIM

**Assessment type:** Portfolio lab control assessment (not a production audit)  
**Scope:** Finance access package, access lifecycle, access reviews, and privileged access via PIM  
**Evidence:** [Existing project README](../README.md) and linked screenshots.

## Risk-to-control mapping

| Risk | Control | Documented lab evidence | Assessment |
|---|---|---|---|
| Unapproved access to sensitive Finance resources | Access package with business justification and administrator approval | Request, approval and Finance group membership screenshots | Request-to-approval-to-provisioning sequence documented |
| Excessive access persists after business need ends | Time-limited assignment and removal workflow | Assignment removal screenshot | Removal demonstrated; ongoing automatic expiration at 30 days not independently verified |
| Users retain access without periodic recertification | Recurring access review | Review frequency and scheduled-review screenshots | Review scheduled; reviewer decision and resulting removal/retention not documented |
| Standing administrator privileges enable misuse | Eligible User Administrator role with PIM approval and time-limited activation | Eligible assignment, request, approval, activation and deactivation screenshots | Temporary activation lifecycle documented; full policy configuration and expiry behavior not independently verified |
| Requester approves own access | Separate requester and administrator approval | Request and approval screenshots | Separation demonstrated in this test flow; broader segregation-of-duties enforcement not independently verified |

## Test procedures and observations

1. **Finance access request:** Review the request, justification, administrator approval, and resulting group membership. **Observed in project:** screenshots document the sequence.
2. **Access removal:** Compare membership before and after assignment removal. **Observed:** removal is documented. **Not established:** automatic expiry after 30 days.
3. **Access review:** Inspect recurrence settings and generated review. **Observed:** scheduling and generation. **Not established:** reviewer certification decisions, application of results, or completion history.
4. **Privileged access:** Trace eligible assignment through activation request, justification, approval, active role, and deactivation. **Observed:** full manually deactivated lifecycle in screenshots. **Not established:** automatic expiry and comprehensive audit-log retention.

## Preliminary findings and recommendations

**IG-001 — Access review effectiveness evidence gap**  
**Type:** Documentation gap; not a confirmed control failure.  
**Observation:** Recurring review was configured and generated, but completed reviewer decisions and outcomes are not shown.  
**Recommendation:** Capture a completed review with redacted reviewer decision and evidence that decisions were applied.

**IG-002 — Automated access expiration not fully demonstrated**  
**Type:** Testing gap; not a confirmed control failure.  
**Observation:** Assignment duration and access removal are documented, but not expiration without manual action.  
**Recommendation:** In a future lab run, allow a short-lived test assignment to expire and record the removal event.

**IG-003 — Privileged activation safeguards require policy-level evidence**  
**Type:** Evidence gap; not a confirmed control failure.  
**Observation:** Justification, approval, activation, and manual deactivation are documented.  
**Recommendation:** Add redacted PIM role settings showing activation duration and applicable MFA requirements, plus relevant audit history if available.

## Assessment conclusion

The lab provides practical evidence of controlled Finance provisioning, assignment removal, access-review scheduling, and approved just-in-time privileged role activation/deactivation. These are relevant to GRC testing of access authorization, least privilege, periodic certification, and privileged access. **Do not represent scheduled reviews as completed reviews, manual deactivation as automatic expiration, or a lab as a formal audit.**

**Portfolio disclosure:** Simulated enterprise workflow in a test Microsoft Entra tenant. Findings describe available documentation and its limitations, not verified production deficiencies.
