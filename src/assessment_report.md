# GitHub Enterprise Copilot Security and Cost Assessment Report

## Executive Summary

- **Assessment scope:** enterprise scope `copilottest008`; organization scope `cloudinfraz`, `cloudinfra008`, `cloudapp007`
- **Assessment date:** 2026-03-29 12:02:18Z
- **Assessor:** GitHub Copilot (GPT-5.4)
- **Overall risk posture:** High
- **Overall maturity estimate:** 1.9 / 5
- **Seat utilization snapshot:** 1/2 active seats (50%) with 1 inactive seat(s) across assessed scope.
- **Repository coverage:** 26 repository record(s) included across sampled organization scope and any direct repository scope.
- **Top three priorities:**
  1. AR-3 — Enterprise evidence for `copilottest008` could not be fully verified because the current account lacks enterprise admin or billing-manager visibility and the `admin:enterprise` scope.
  2. DC-4 — Seat assignment is not consistently controlled through selected-seat workflows across `enterprise:copilottest008`, `cloudinfraz`, `cloudapp007`.
  3. BP-3 — Public-code suggestion controls are not strongly restricted across `enterprise:copilottest008`, `cloudinfraz`.

## Scope and Methodology

### Scope

- In-scope accessible scope for this run: enterprise scope `copilottest008`; organization scope `cloudinfraz`, `cloudinfra008`, `cloudapp007`.
- The assessment covered enterprise billing or inheritance evidence where accessible, organization billing posture, seat allocation, Copilot metrics samples, audit-log activity, organization metadata, and repository security control evidence.
- Enterprise-wide legal/compliance documents, training materials, and formal governance artifacts were only included when accessible through the current account context or supplied externally.

### Methodology

- Read-only GitHub CLI API calls were used to collect enterprise, organization, seat, metrics, audit-log, and repository control evidence using `GET-only` requests only.
- No write privileges were assumed beyond the current account context.
- The script does not invoke POST, PATCH, PUT, or DELETE operations against enterprise, organization, or repository settings.
- Remediation content is emitted as `proposed-only` guidance only; the assessment does not change any GitHub configuration directly.
- Security domains use all assessed enterprise and org scope, while usage-heavy interpretations lean on scopes with active seats when present.
- Missing documents were treated as evidence gaps rather than assumed compliant. Security fairy dust was not applied.

## Live Enterprise Snapshot

| Enterprise | Display Name | Plan | Total Seats | Active Seats | Utilization | Seat Management | Visible Orgs | Metrics | Audit Sample |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| copilottest008 | copilottest008 | unknown | 0 | 0 | n/a | unknown | 0 | unavailable | no |

## Live Organization Snapshot

| Organization | Role | Plan | Total Seats | Active Seats | Utilization | Seat Management | Public Code Suggestions | Default Repo Permission | 2FA Required | Enabled Features |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cloudinfraz | admin | business | 0 | 0 | n/a | unconfigured | unconfigured | read | no | none |
| cloudinfra008 | admin | business | 2 | 1 | 50% | assign_selected | block | read | no | ide_chat, cli, platform_chat |
| cloudapp007 | admin | business | 0 | 0 | n/a | unconfigured | block | read | no | ide_chat, platform_chat |

## Cost Optimization Summary

| Scope | Total Seats | Active Seats | Seats Without Activity | Utilization | Metrics | Cost Posture | Recommendation |
| --- | --- | --- | --- | --- | --- | --- | --- |
| enterprise:copilottest008 | 0 | 0 | 0 | n/a | unavailable | No current seat spend | No current seat spend; keep explicit settings and governance in place before any rollout. |
| cloudinfraz | 0 | 0 | 0 | n/a | unavailable | No current seat spend | No current seat spend; keep explicit settings and governance in place before any rollout. |
| cloudinfra008 | 2 | 1 | 1 | 50% | available | Review | Review 1 seat(s) with no recent activity and reassign or remove if not needed. |
| cloudapp007 | 0 | 0 | 0 | n/a | unavailable | No current seat spend | No current seat spend; keep explicit settings and governance in place before any rollout. |

## Repository Security Control Snapshot

| Source | Owner | Repository | Visibility | Branch Protected | Secret Scanning | Push Protection | Dependabot Updates | Delete Branch On Merge |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| organization-sampled | cloudinfraz | s3proxy-rs | private | no | disabled | disabled | enabled | no |
| organization-sampled | cloudinfraz | TechWorkshop-L300-GitHub-Copilot-and-platform | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | barter-rs | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | algo-trading | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | istio-lab | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | pytrader | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | rocky9-scripts | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | centos8 | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | Awesome-PyTorch-Chinese | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | DeepLearningExamples | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | field-workshops-terraform | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | gitops-flux2-kustomize-helm-mt | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | redis-operator | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | sandboxed-containers-operator | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | hyperkube | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | operationalizing-openshift-lab | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | kube-ovn | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | kubestone | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | hybrid-cloud-serverless | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | knative-tutorial | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | ocp4 | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | svt | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | ansible-tower-offline | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | ocp4-automatic-approval-helper | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfraz | Terraform-learning | public | no | disabled | disabled | disabled | no |
| organization-sampled | cloudinfra008 | skills-getting-started-with-github-copilot | public | no | enabled | enabled | disabled | no |

## Domain Summary Table

| Domain | Maturity Score (0-5) | Risk Level | Key Observation |
| --- | --- | --- | --- |
| Deployment and configuration | 2 | Moderate | Rollout scope, repo protections, and feature settings are only partly intentional across accessible enterprise, organization, and repository scope. |
| Security best practices | 2 | Moderate | Selected-seat assignment, public-code blocking, and baseline admin controls are inconsistent across assessed scope. |
| Vulnerability exposure | 2 | Moderate | Repository security controls are uneven; branch protection and dependency security need strengthening. |
| Monitoring and incident response | 2 | Moderate | Audit events are partly visible, and metrics may be available, but incident playbooks remain unverified. |
| Compliance | 2 | Moderate | Technical outputs alone do not satisfy compliance or data-classification expectations. |
| Risk management | 1 | High | Formal Copilot risk ownership and acceptance remain undocumented. |
| Audit and review | 2 | Moderate | Evidence can be exported, but recurring review and exception handling are not yet demonstrated. |
| Policy and governance | 2 | Moderate | Governance is partially visible technically, but not yet backed by documented policy ownership. |

## Control Gap Register and Implementation Plan

| Priority | Control | Domain | Gap | Implementation Plan | Owner | Target Window | Validation |
| --- | --- | --- | --- | --- | --- | --- | --- |
| P1 | AR-3 | Audit and review | Enterprise evidence for `copilottest008` could not be fully verified because the current account lacks enterprise admin or billing-manager visibility and the `admin:enterprise` scope. | 1. Refresh GitHub CLI authentication with `admin:enterprise` and use an enterprise owner or billing-manager account.<br>2. Re-run the assessment and archive enterprise billing, seat, metrics, audit-log, and organization inventory exports.<br>3. Record who owns the recurring enterprise evidence export and where the evidence pack is stored. | Enterprise owner / GitHub enterprise admin | 0-30 days | Enterprise raw JSON no longer contains 403/404 auth errors for billing, seats, metrics, audit, and organization inventory endpoints. |
| P2 | DC-4 | Deployment and configuration | Seat assignment is not consistently controlled through selected-seat workflows across `enterprise:copilottest008`, `cloudinfraz`, `cloudapp007`. | 1. Move all accessible enterprise and org scope to selected-seat assignment rather than broad default enablement.<br>2. Define joiner, mover, and leaver steps for Copilot seat approval, removal, and periodic revalidation.<br>3. Review seat holders with no recent activity and remove or reassign unused licenses before expanding spend. | Copilot admin / Identity governance / Engineering management | 0-30 days | Billing snapshots show `assign_selected`, and inactive or no-activity seats are reduced to an approved baseline. |
| P3 | BP-3 | Security best practices | Public-code suggestion controls are not strongly restricted across `enterprise:copilottest008`, `cloudinfraz`. | 1. Set public-code suggestions to the approved restrictive mode for all accessible scope unless a documented exception exists.<br>2. Update developer guidance so generated code is treated as untrusted until reviewed, tested, and provenance-checked.<br>3. Add pull request checklist language requiring reviewers to verify generated snippets for licensing, security, and correctness. | AppSec / Copilot governance owner / Developer experience | 0-30 days | Billing settings show blocked public-code suggestions and the PR template or review standard includes generated-code review expectations. |
| P4 | BP-1 | Security best practices | Member 2FA is not enforced in `cloudinfraz`, `cloudinfra008`, `cloudapp007`. | 1. Enable organization-wide 2FA enforcement for all members and admins.<br>2. Review owner and admin role assignments for least privilege and remove broad admin access that is not operationally required.<br>3. Document a quarterly access review covering Copilot admins, organization owners, and repository administrators. | Org owner / Identity and access management | 0-30 days | Org metadata returns `two_factor_requirement_enabled=true`, and access review evidence is stored for the quarter. |
| P5 | VA-4 | Vulnerability exposure | Branch protection or equivalent change-control enforcement is missing on 26 assessed repositories, including `cloudinfraz/s3proxy-rs`, `cloudinfraz/TechWorkshop-L300-GitHub-Copilot-and-platform`, `cloudinfraz/barter-rs`, `cloudinfraz/algo-trading`, `cloudinfraz/istio-lab`, … (+21 more). | 1. Apply branch protection or repository rulesets that require pull requests, status checks, and review before merge.<br>2. Use a baseline ruleset for all repositories that accept Copilot-assisted code and tighten controls for production or regulated repos.<br>3. Track exceptions centrally and require time-bound approval for any repo that cannot meet the baseline. | Platform engineering / Repository owners | 30-90 days | All assessed repositories show branch protection or an approved equivalent ruleset on the default branch. |
| P6 | VA-1 | Vulnerability exposure | Automated scanning coverage is incomplete on 26 assessed repositories, including `cloudinfraz/s3proxy-rs`, `cloudinfraz/TechWorkshop-L300-GitHub-Copilot-and-platform`, `cloudinfraz/barter-rs`, `cloudinfraz/algo-trading`, `cloudinfraz/istio-lab`, … (+21 more). | 1. Enable Dependabot security updates, dependency graph, and secret scanning for repositories that handle Copilot-assisted changes.<br>2. Add code scanning where supported and require findings to be triaged before merge for higher-risk repositories.<br>3. Create a baseline repository-security standard that new repositories inherit by default. | AppSec / Platform engineering / Repository owners | 30-90 days | Repository snapshots show `dependabot_security_updates=enabled` and `secret_scanning=enabled` for in-scope repositories or documented exceptions exist. |
| P7 | AR-4 | Audit and review | Usage and assurance reviews are weakened because Copilot metrics are unavailable or inaccessible for `enterprise:copilottest008`. | 1. Restore access to the highest available metrics source or define a replacement telemetry export before the legacy metrics API sunsets.<br>2. Link usage reviews to seat-rightsizing, governance meetings, and quarterly assurance evidence packs.<br>3. Record thresholds for inactive seats, low-adoption groups, and unusual usage spikes that trigger review. | Copilot admin / Governance / FinOps | 30-90 days | A recurring usage dashboard or exported report exists and is referenced in quarterly review records. |
| P8 | MI-1 | Monitoring and incident response | Copilot-related audit visibility is incomplete for `enterprise:copilottest008`, `cloudinfraz`. | 1. Confirm which enterprise and org audit events are retained and exportable for Copilot, policy changes, workflows, and rulesets.<br>2. Forward relevant audit events to SIEM or log analytics with retention aligned to investigation requirements.<br>3. Define alerts for policy changes, broad seat assignment changes, and suspicious repository-control drift. | Security operations / GitHub administrators | 30-90 days | Audit events are exportable for in-scope enterprise and orgs, and monitoring rules exist for key Copilot or policy-change events. |
| P9 | BP-2 | Security best practices | No developer-facing secure-use guidance, prompt hygiene standard, or generated-code review standard was supplied to the assessment. | 1. Publish a Copilot secure-use standard covering prompt hygiene, prohibited data, generated-code review, and safe extension or agent usage.<br>2. Train developers and reviewers to treat generated output as untrusted until reviewed, tested, and scanned.<br>3. Embed the guidance in onboarding, repository templates, and pull request review checklists. | Developer experience / AppSec | 30-90 days | Training material, secure-use guidance, and repository or PR templates are versioned and referenced in the evidence pack. |
| P10 | MI-2 | Monitoring and incident response | No Copilot-specific incident response playbook, escalation path, or data-leakage response workflow was supplied to the assessment. | 1. Create an incident playbook for prompt leakage, unsafe generated content, compromised integrations, and agent or MCP misuse.<br>2. Define triage roles, legal and privacy escalation paths, and evidence-preservation steps.<br>3. Run a tabletop exercise and capture follow-up actions in the governance backlog. | Security operations / Privacy / Legal / AppSec | 30-90 days | A versioned playbook exists, contacts are named, and at least one exercise or walkthrough has been completed. |
| P11 | CO-1 | Compliance | No compliance control mapping, data-classification rules, or regulated-environment overlays were supplied to the technical assessment. | 1. Map Copilot controls to the organization's governing frameworks such as ISO 27001, SOC 2, NIST, or internal standards.<br>2. Document what code, secrets, customer data, and regulated content types are prohibited, restricted, or approved for Copilot.<br>3. Define stricter overlays or exclusions for regulated repositories, environments, and business units. | Compliance / Security governance / Legal | 90+ days | A control mapping and acceptable-use classification matrix is approved and referenced by governance reviews. |
| P12 | RM-1 | Risk management | No formal risk register entries, named risk owners, or feature-rollout approval records were supplied for Copilot. | 1. Create formal Copilot risk register entries that cover data leakage, insecure generated code, governance drift, and unsafe agent tooling.<br>2. Assign risk owners, control owners, and decision-makers for new feature rollout approvals.<br>3. Require documented risk review before enabling advanced capabilities such as coding agents, MCP integrations, or broad enterprise rollout. | Risk management / Governance board / Engineering leadership | 90+ days | Risk register entries exist with named owners, review dates, residual risk decisions, and rollout-approval references. |
| P13 | PG-1 | Policy and governance | No governance charter, policy versioning model, or enterprise-versus-organization inheritance documentation was supplied. | 1. Define a Copilot governance charter that names who can enable, monitor, approve, and exception-handle capabilities.<br>2. Version policies and record enterprise-versus-organization inheritance decisions, including approved deviations.<br>3. Establish a recurring governance forum with business, legal, security, and engineering stakeholders. | Security governance / Enterprise owner / Engineering leadership | 90+ days | A versioned governance charter, policy repository, and meeting cadence exist and are reflected in review records. |
| P14 | AR-1 | Audit and review | No recurring review cadence, exception register, or reapproval workflow was supplied for Copilot controls. | 1. Create a quarterly Copilot review pack that includes settings exports, seat metrics, repository-control posture, exceptions, and owner attestations.<br>2. Maintain an exception register with expiry dates, compensating controls, and reapproval requirements.<br>3. Tie the review outcome to backlog items and governance decisions rather than a one-off assessment artifact. | Security governance / Internal audit / Copilot admin | 90+ days | Quarterly review artifacts and an exception register exist with dated approvals and follow-up actions. |

### Read-only and implementation guardrails

- Collection mode: `read-only` using `GET-only` GitHub API requests only.
- Remediation execution mode: `proposed-only`; every action below is a proposed implementation plan, not an automated change.
- Best-practice basis: GitHub Enterprise Copilot control catalog plus GitHub/Microsoft secure-use, least-privilege, review-gate, and governance guidance.

## Detailed Findings

### 1. Deployment and Configuration Assessment

- **Current state:** Accessible enterprise, organization, and repository scope shows partially intentional Copilot rollout and partially hardened repository posture.
- **Evidence reviewed:** Enterprise or organization billing snapshots, seat assignment endpoints, metrics samples, organization metadata, and repository control samples.
- **Strengths:**
  - `cloudinfraz` keeps the default repository permission at `read`, which is a safer default for broad membership.
  - `cloudinfra008` uses selected-seat assignment rather than broad auto-assignment.
  - `cloudinfra008` blocks public code suggestions, reducing code provenance risk.
  - `cloudinfra008` exposes Copilot usage metrics for date `2026-03-26`, supporting seat review and ROI tracking.
  - `cloudinfra008` has visible audit evidence, including: copilot.cfb_org_settings_changed, workflows.completed_workflow_run, workflows.prepared_workflow_job.
  - `cloudinfra008` keeps the default repository permission at `read`, which is a safer default for broad membership.
- **Gaps:**
  - Enterprise `copilottest008` shows `unknown` seat management, which is weak or incomplete for controlled rollout.
  - Enterprise `copilottest008` does not show a strong public-code-suggestions restriction.
  - Enterprise `copilottest008` does not provide accessible Copilot metrics in this run.
  - Enterprise `copilottest008` has no accessible Copilot audit event sample in this run.
  - Enterprise `copilottest008` did not return accessible enterprise organization inventory in this run.
  - `cloudinfraz` shows `unconfigured` seat management, which is weak or incomplete for controlled rollout.
- **Risk level:** Moderate
- **Recommended actions:** Explicitly configure every enterprise and org seat assignment model and feature state, and keep repository protection baselines aligned before broad rollout.

### 2. Security Best Practices Assessment

- **Current state:** Technical best practices are partially visible through selected-seat assignment, public-code blocking, 2FA posture, and default repository permissions, but user guidance and advanced-feature approvals remain undocumented.
- **Evidence reviewed:** Enterprise and org policy flags, seat allocation patterns, metrics availability, and org metadata.
- **Strengths:** Controlled rollout evidence exists where selected-seat assignment and blocked public-code suggestions are configured.
- **Gaps:** No developer training, prompt-handling guidance, extension approval policy, or secure-use standard was supplied.
- **Risk level:** Moderate
- **Recommended actions:** Publish secure-use guidance, require generated-code review in pull requests, and define approval paths for coding agent, MCP, and other higher-risk features.

### 3. Security Vulnerability Assessment

- **Current state:** Repository security controls are uneven. Secret scanning is present in some accessible repositories, but branch protection and Dependabot security updates are not consistently enabled.
- **Evidence reviewed:** Enterprise or org audit events showing workflow or ruleset activity, plus repository security control samples and direct repository checks.
- **Strengths:** Accessible repositories expose concrete secret-scanning and branch-protection evidence instead of purely narrative claims.
- **Gaps:** Dependabot security updates and branch protection remain incomplete in sampled repositories, which weakens the control path for Copilot-assisted code.
- **Risk level:** Moderate
- **Recommended actions:** Require branch protection or equivalent rulesets, verify code scanning where applicable, and enable Dependabot security updates for repositories accepting Copilot-generated changes.

### 4. Security Monitoring and Incident Response Assessment

- **Current state:** Monitoring is partially evidenced because Copilot-related settings changes may be visible in enterprise or organization audit logs and metrics may be available for seat or activity review.
- **Evidence reviewed:** Sampled enterprise or organization audit-log events and Copilot metrics outputs.
- **Strengths:** The assessment can export technical monitoring evidence at the highest accessible scope.
- **Gaps:** No SIEM forwarding, alert definitions, retention standards, or incident response playbooks were reviewed.
- **Risk level:** Moderate
- **Recommended actions:** Forward Copilot-related audit events to your monitoring platform, define alert rules, and create an incident runbook for misuse, prompt leakage, and unsafe agent or tool behavior.

### 5. Security Compliance Assessment

- **Current state:** Compliance posture could not be substantiated from technical APIs alone.
- **Evidence reviewed:** Technical configuration outputs only; no compliance documents were supplied.
- **Strengths:** Blocking public-code matches, requiring 2FA, and maintaining exportable evidence helps but does not replace formal compliance mapping.
- **Gaps:** No framework mapping (ISO 27001, SOC 2, NIST, GDPR, HIPAA, etc.), data classification rules, or regulated environment exclusions were provided.
- **Risk level:** Moderate
- **Recommended actions:** Map Copilot controls to your compliance framework and document what code or data classes are prohibited, restricted, or approved for Copilot use.

### 6. Security Risk Management Assessment

- **Current state:** No formal risk-management artifacts were available during this assessment.
- **Evidence reviewed:** Enterprise and organization posture signals, seat-assignment patterns, and baseline identity controls.
- **Strengths:** Selected-seat assignment is a better risk posture than broad default enablement.
- **Gaps:** No risk register entries, named control owners, residual-risk acceptances, or rollout-approval records were supplied.
- **Risk level:** High
- **Recommended actions:** Add Copilot risks to the enterprise risk register, assign owners, and require change or risk review before enabling new Copilot capabilities at scale.

### 7. Security Audit and Review Assessment

- **Current state:** Auditability is possible because relevant settings, usage, organization metadata, and repository evidence can be exported, but recurring review practice was not demonstrated.
- **Evidence reviewed:** Enterprise endpoints where accessible, org billing endpoints, seat endpoints, metrics outputs, repo samples, and audit-log event samples.
- **Strengths:** The environment supports evidence collection at more than one scope without requiring manual screenshots for every control.
- **Gaps:** No review cadence, exception register, or assurance metrics pack was supplied.
- **Risk level:** Moderate
- **Recommended actions:** Establish a quarterly Copilot review pack with exported enterprise and org settings, usage summaries, repository control checks, exceptions, and attestation from owners.

### 8. Security Policy and Governance Assessment

- **Current state:** Governance appears partially operational in accessible scope but remains weakly evidenced overall.
- **Evidence reviewed:** Seat assignment mode, policy states, metrics visibility, Copilot settings change events, and org baseline settings such as default repository permission and 2FA requirement.
- **Strengths:** Policy changes are traceable in audit logs where accessible, and at least part of the scope uses a controlled seat-assignment model with measurable usage.
- **Gaps:** No governance charter, policy repository, approval matrix, or enterprise-vs-org inheritance documentation was reviewed.
- **Risk level:** Moderate
- **Recommended actions:** Define governance ownership, publish versioned Copilot policy, and require enterprise and org admins to document deviations from the baseline.

## Prioritized Remediation Roadmap

### Immediate Actions (0-30 days)

| Priority | Action | Owner | Target Date | Expected Benefit |
| --- | --- | --- | --- | --- |
| P1 | Enterprise evidence for `copilottest008` could not be fully verified because the current account lacks enterprise admin or billing-manager visibility and the `admin:enterprise` scope. | Enterprise owner / GitHub enterprise admin | 0-30 days | Enterprise raw JSON no longer contains 403/404 auth errors for billing, seats, metrics, audit, and organization inventory endpoints. |
| P2 | Seat assignment is not consistently controlled through selected-seat workflows across `enterprise:copilottest008`, `cloudinfraz`, `cloudapp007`. | Copilot admin / Identity governance / Engineering management | 0-30 days | Billing snapshots show `assign_selected`, and inactive or no-activity seats are reduced to an approved baseline. |
| P3 | Public-code suggestion controls are not strongly restricted across `enterprise:copilottest008`, `cloudinfraz`. | AppSec / Copilot governance owner / Developer experience | 0-30 days | Billing settings show blocked public-code suggestions and the PR template or review standard includes generated-code review expectations. |
| P4 | Member 2FA is not enforced in `cloudinfraz`, `cloudinfra008`, `cloudapp007`. | Org owner / Identity and access management | 0-30 days | Org metadata returns `two_factor_requirement_enabled=true`, and access review evidence is stored for the quarter. |

### Near-Term Improvements (30-90 days)

| Priority | Action | Owner | Target Date | Expected Benefit |
| --- | --- | --- | --- | --- |
| P5 | Branch protection or equivalent change-control enforcement is missing on 26 assessed repositories, including `cloudinfraz/s3proxy-rs`, `cloudinfraz/TechWorkshop-L300-GitHub-Copilot-and-platform`, `cloudinfraz/barter-rs`, `cloudinfraz/algo-trading`, `cloudinfraz/istio-lab`, … (+21 more). | Platform engineering / Repository owners | 30-90 days | All assessed repositories show branch protection or an approved equivalent ruleset on the default branch. |
| P6 | Automated scanning coverage is incomplete on 26 assessed repositories, including `cloudinfraz/s3proxy-rs`, `cloudinfraz/TechWorkshop-L300-GitHub-Copilot-and-platform`, `cloudinfraz/barter-rs`, `cloudinfraz/algo-trading`, `cloudinfraz/istio-lab`, … (+21 more). | AppSec / Platform engineering / Repository owners | 30-90 days | Repository snapshots show `dependabot_security_updates=enabled` and `secret_scanning=enabled` for in-scope repositories or documented exceptions exist. |
| P7 | Usage and assurance reviews are weakened because Copilot metrics are unavailable or inaccessible for `enterprise:copilottest008`. | Copilot admin / Governance / FinOps | 30-90 days | A recurring usage dashboard or exported report exists and is referenced in quarterly review records. |
| P8 | Copilot-related audit visibility is incomplete for `enterprise:copilottest008`, `cloudinfraz`. | Security operations / GitHub administrators | 30-90 days | Audit events are exportable for in-scope enterprise and orgs, and monitoring rules exist for key Copilot or policy-change events. |
| P9 | No developer-facing secure-use guidance, prompt hygiene standard, or generated-code review standard was supplied to the assessment. | Developer experience / AppSec | 30-90 days | Training material, secure-use guidance, and repository or PR templates are versioned and referenced in the evidence pack. |
| P10 | No Copilot-specific incident response playbook, escalation path, or data-leakage response workflow was supplied to the assessment. | Security operations / Privacy / Legal / AppSec | 30-90 days | A versioned playbook exists, contacts are named, and at least one exercise or walkthrough has been completed. |

### Strategic Enhancements (90+ days)

| Priority | Action | Owner | Target Date | Expected Benefit |
| --- | --- | --- | --- | --- |
| P11 | No compliance control mapping, data-classification rules, or regulated-environment overlays were supplied to the technical assessment. | Compliance / Security governance / Legal | 90+ days | A control mapping and acceptable-use classification matrix is approved and referenced by governance reviews. |
| P12 | No formal risk register entries, named risk owners, or feature-rollout approval records were supplied for Copilot. | Risk management / Governance board / Engineering leadership | 90+ days | Risk register entries exist with named owners, review dates, residual risk decisions, and rollout-approval references. |
| P13 | No governance charter, policy versioning model, or enterprise-versus-organization inheritance documentation was supplied. | Security governance / Enterprise owner / Engineering leadership | 90+ days | A versioned governance charter, policy repository, and meeting cadence exist and are reflected in review records. |
| P14 | No recurring review cadence, exception register, or reapproval workflow was supplied for Copilot controls. | Security governance / Internal audit / Copilot admin | 90+ days | Quarterly review artifacts and an exception register exist with dated approvals and follow-up actions. |

## Evidence Gaps and Open Questions

- Missing evidence: enterprise-wide policy inheritance, training records, risk register, compliance mappings, incident response playbooks, and approved exception records.
- Unverified assumptions: API-visible settings are representative of intended policy posture, and the sampled repositories are representative of the broader organization security baseline.
- Follow-up interviews required: enterprise owner, security operations, AppSec, compliance, finance or engineering management, and the Copilot governance owner.
- Additional technical validation recommended: broader repository sampling, code-scanning verification, SIEM ingestion checks, and replacement telemetry for the legacy Copilot metrics API before its sunset.

## Appendix

### Evidence Inventory

| Evidence Item | Source | Date Reviewed | Notes |
| --- | --- | --- | --- |
| Enterprise info for `copilottest008` | `/enterprises/copilottest008` | 2026-03-29 12:02:18Z | Live REST API output via gh |
| Enterprise Copilot billing snapshot for `copilottest008` | `/enterprises/copilottest008/copilot/billing` | 2026-03-29 12:02:18Z | Live REST API output via gh |
| Enterprise seat assignments for `copilottest008` | `/enterprises/copilottest008/copilot/billing/seats` | 2026-03-29 12:02:18Z | Live REST API output via gh |
| Enterprise Copilot metrics sample for `copilottest008` | `/enterprises/copilottest008/copilot/metrics?per_page=1` | 2026-03-29 12:02:18Z | unavailable |
| Enterprise audit events for `copilottest008` | `/enterprises/copilottest008/audit-log?phrase=copilot` | 2026-03-29 12:02:18Z | Live REST API output via gh (sampled) |
| Enterprise organization inventory for `copilottest008` | `/enterprises/copilottest008/organizations?per_page=100` | 2026-03-29 12:02:18Z | Used to validate accessible org scope and inheritance evidence |
| Organization metadata for `cloudinfraz` | `/orgs/cloudinfraz` | 2026-03-29 12:02:18Z | Used for default repository permission and 2FA evidence |
| Copilot billing snapshot for `cloudinfraz` | `/orgs/cloudinfraz/copilot/billing` | 2026-03-29 12:02:18Z | Live REST API output via gh |
| Seat assignments for `cloudinfraz` | `/orgs/cloudinfraz/copilot/billing/seats` | 2026-03-29 12:02:18Z | Live REST API output via gh |
| Copilot metrics sample for `cloudinfraz` | `/orgs/cloudinfraz/copilot/metrics?per_page=1` | 2026-03-29 12:02:18Z | unavailable |
| Audit events for `cloudinfraz` | `/orgs/cloudinfraz/audit-log?phrase=copilot` | 2026-03-29 12:02:18Z | Live REST API output via gh (sampled) |
| Repository control scope for `cloudinfraz` | `/orgs/cloudinfraz/repos?type=all&sort=updated` | 2026-03-29 12:02:18Z | Includes all accessible repositories per organization, security_and_analysis metadata, and branch protection checks |
| Organization metadata for `cloudinfra008` | `/orgs/cloudinfra008` | 2026-03-29 12:02:18Z | Used for default repository permission and 2FA evidence |
| Copilot billing snapshot for `cloudinfra008` | `/orgs/cloudinfra008/copilot/billing` | 2026-03-29 12:02:18Z | Live REST API output via gh |
| Seat assignments for `cloudinfra008` | `/orgs/cloudinfra008/copilot/billing/seats` | 2026-03-29 12:02:18Z | Live REST API output via gh |
| Copilot metrics sample for `cloudinfra008` | `/orgs/cloudinfra008/copilot/metrics?per_page=1` | 2026-03-29 12:02:18Z | available |
| Audit events for `cloudinfra008` | `/orgs/cloudinfra008/audit-log?phrase=copilot` | 2026-03-29 12:02:18Z | Live REST API output via gh (sampled) |
| Repository control scope for `cloudinfra008` | `/orgs/cloudinfra008/repos?type=all&sort=updated` | 2026-03-29 12:02:18Z | Includes all accessible repositories per organization, security_and_analysis metadata, and branch protection checks |
| Organization metadata for `cloudapp007` | `/orgs/cloudapp007` | 2026-03-29 12:02:18Z | Used for default repository permission and 2FA evidence |
| Copilot billing snapshot for `cloudapp007` | `/orgs/cloudapp007/copilot/billing` | 2026-03-29 12:02:18Z | Live REST API output via gh |
| Seat assignments for `cloudapp007` | `/orgs/cloudapp007/copilot/billing/seats` | 2026-03-29 12:02:18Z | Live REST API output via gh |
| Copilot metrics sample for `cloudapp007` | `/orgs/cloudapp007/copilot/metrics?per_page=1` | 2026-03-29 12:02:18Z | unavailable |
| Audit events for `cloudapp007` | `/orgs/cloudapp007/audit-log?phrase=copilot` | 2026-03-29 12:02:18Z | Live REST API output via gh (sampled) |
| Repository control scope for `cloudapp007` | `/orgs/cloudapp007/repos?type=all&sort=updated` | 2026-03-29 12:02:18Z | Includes all accessible repositories per organization, security_and_analysis metadata, and branch protection checks |

### Control References

Referenced controls: `DC-1` through `DC-4`, `BP-1` through `BP-4`, `VA-1` through `VA-4`, `MI-1` through `MI-4`, `CO-1` through `CO-4`, `RM-1` through `RM-4`, `AR-1` through `AR-4`, and `PG-1` through `PG-4` from the skill control catalog.
