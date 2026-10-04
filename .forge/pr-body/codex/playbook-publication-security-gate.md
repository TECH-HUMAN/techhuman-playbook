# fix(ci): block Playbook publication when dependency audit fails

The scheduled distributor reads `th-new-business-model/main` every six hours. Its check/build/export command does not audit dependencies, so the current vulnerable canonical lock could reach Pages even while the separate Docs publisher is blocked.

Add a complete `npm audit --audit-level=moderate` step after the frozen installation and before build or artifact upload. The explicit endpoint is the public npm registry. Development, production and optional dependencies remain included. A nonzero audit exit fails the build job; deployment still depends on that job. No `continue-on-error`, skipped advisory, narrowed dependency set or risk waiver is added.

Preserve the canonical source/ref, schedule, action pins, Node version, permissions, environment, domain, artifact checks and deployment chain. This change does not edit the institutional content or remediate its dependencies. The observed canonical Playbook lock currently produces exit 1: one critical, three high and one moderate affected package. Therefore publication remains blocked until a separately qualified dependency correction passes the complete audit.

Validation: structural workflow comparison and the real current canonical audit, with lock/source hashes and nonzero exit recorded in the external October implementation receipt. No workflow dispatch, merge, Pages upload or deployment was executed for this candidate. The source narrative PR remains separate: https://github.com/TECH-HUMAN/th-new-business-model/pull/156.

Tracking: https://github.com/needyuai/trustyu-docs/issues/865 and https://github.com/needyuai/trustyu-docs/issues/868. Publication is a separate gate from source integration and does not prove GA, access or service readiness.

---

Origin: Codex (OpenAI), user-authorized October 2026 strategy continuation. Owner authorization is the human instruction in the conversation; technical root/peer review is recorded separately and does not impersonate a human GitHub approval.
