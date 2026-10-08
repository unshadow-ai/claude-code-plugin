# Unshadow for claude-code (developer preview)

Self-contained Node 22+ memory integration. The private monorepo is not included.

Clone this repository and check out the full commit SHA shown in its release. Add the local clone with `claude plugin marketplace add <absolute-clone-path>`, then run `claude plugin install unshadow-memory@unshadow`. Review hook trust through the host normally.

Read the bundled plugin README for project-key setup, opt-outs and diagnostics. Completed user/assistant turns are sanitized and queued durably. Public native model chats and comparative quality remain unverified; this release is a developer preview.
