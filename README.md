Your agent's rules live in its prompt, and prompts get trimmed. I build [Fiduciary](https://github.com/crimsondevil0929/fiduciary), open-source Python (`interlock-fiduciary`) that sits between an AI agent and its tools and systems: MCP servers, REST APIs, Git repositories, directories, Kubernetes and Terraform, FHIR servers, and SQL databases.

Fiduciary pins tool definitions and server package versions, moves server tokens out of client files into the OS secret store, holds destructive calls for your hardware passkey, blocks credentials and private data from leaving across servers or agent memory sessions, puts back what a failed turn changed, and leaves a signed record anyone can verify offline (`V1` to `V14`).

<table>
<tr>
<td width="76" align="center"><a href="https://github.com/crimsondevil0929/fiduciary"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/fiduciary-dark.svg"><img src="assets/fiduciary.svg" width="48" height="48" alt="Fiduciary"></picture></a></td>
<td><a href="https://github.com/crimsondevil0929/fiduciary"><b>Fiduciary</b></a> &nbsp;<code>pip install interlock-fiduciary</code><br>
Start here: one command (<code>fiduciary protect</code>) wraps local and remote MCP servers for Claude Desktop, Cursor, Claude Code, VS Code and Codex, enforces passkey holds, outbound control, cross-session memory provenance and <code>fiduciary ci</code>, and installs both engines below.</td>
</tr>
<tr>
<td width="76" align="center"><a href="https://github.com/crimsondevil0929/interlock"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/interlock-dark.svg"><img src="assets/interlock.svg" width="48" height="48" alt="Interlock"></picture></a></td>
<td><a href="https://github.com/crimsondevil0929/interlock"><b>Interlock</b></a> &nbsp;<code>interlock-escrow</code><br>
Staging and measurement engine: stages each write across SQL, Git, directories, Kubernetes, Terraform, FHIR and REST, measures what changed, and puts it back with exact <code>fiduciary undo</code> or retry-safe Class V compensation.</td>
</tr>
<tr>
<td width="76" align="center"><a href="https://github.com/crimsondevil0929/agentgov"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/agentgov-dark.svg"><img src="assets/agentgov.svg" width="48" height="48" alt="AgentGov"></picture></a></td>
<td><a href="https://github.com/crimsondevil0929/agentgov"><b>AgentGov</b></a> &nbsp;<code>interlock-agentgov</code><br>
Budget and telemetry engine: holds spend limits, rate windows and circuit breakers across delegation trees, records ARC1 receipts, and reconciles external system logs.</td>
</tr>
</table>

**See it live (browser verifier, recorded runs, and benchmarks):**
- [Live 8-workflow workbench & WebCrypto bundle verifier](https://crimsondevil0929.github.io/fiduciary/)
- [Three public incident replays](https://crimsondevil0929.github.io/fiduciary/replays/) (`delete_volume`, cross-server toxic flow, silent MCP update)
- [Commit-pinned benchmarks and limits](https://crimsondevil0929.github.io/fiduciary/benchmarks/) (`1.60 ms` P50 SQLite stage/diff/commit, `0.11 ms` P50 layered egress scan, `0.02 ms` P50 memory recall)

**Try it in 60 seconds** (shadow mode watches and reports without refusing anything until you run `--enforce`; Python SDK `@gov.tool` and GitHub Actions `uses: crimsondevil0929/fiduciary@v1.21.0` work the same way):

```bash
pip install interlock-fiduciary
fiduciary protect --claude-desktop            # or --cursor, --vscode, --codex, --mcp-config .mcp.json --claude-code
fiduciary protect --claude-desktop --apply    # wrap every MCP server in shadow mode
fiduciary replay all                          # run 3 public incident reconstructions locally
```
