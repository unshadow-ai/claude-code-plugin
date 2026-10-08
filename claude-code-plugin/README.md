# unshadow-memory (preview)

Build with `node scripts/developer-platform/build-p17-agents.mjs` from the private source repository. The disposable output contains a self-contained plugin with runtime.mjs; source wrappers alone are not an installable release. No monorepo export is required.

Use the host native local plugin install/load flow and review its hooks normally. Run `node <plugin>/scripts/agent.mjs login --host=claude-code` in a repository, providing a project key on stdin. Set UNSHADOW_API_KEY or use the protected local credential mapping; avoid a key in shell arguments. Node 22+ is required. Hooks never open a browser or change trust settings.

SessionStart recalls project context; UserPromptSubmit recalls and stores a sanitized pending prompt; Stop pairs it with last_assistant_message. No transcript parser, tool output, or subagent transcript is used. SessionEnd drains queued completed captures only. Interrupted prompts are not labelled completed turns. Read-only keys do not capture. Explicit opt-outs persist through login --no-capture / --no-recall.

Commands: login/setup, status, logout, search <query>, save (stdin), init (explicit architecture text on stdin). Logout removes this repository mapping but preserves the outbox; revoke the key in the dashboard to invalidate credentials everywhere. Live native chat and public installation remain unverified; preview support only.
