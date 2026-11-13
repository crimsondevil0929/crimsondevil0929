I write open-source Python for AI agents that change real systems: databases, repositories,
directories, clusters, FHIR servers and REST APIs. Each change an agent makes through them is
staged, measured and checked against limits a person signed, and anyone with the public keys
can check the record offline. Three packages make one stack:

<table>
<tr>
<td width="76" align="center"><a href="https://github.com/crimsondevil0929/fiduciary"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/fiduciary-dark.svg"><img src="assets/fiduciary.svg" width="48" height="48" alt="Fiduciary"></picture></a></td>
<td><a href="https://github.com/crimsondevil0929/fiduciary"><b>Fiduciary</b></a> &nbsp;<code>pip install interlock-fiduciary</code><br>
Signed limits for AI agents that change real systems, and proof anyone can check offline.
Start here: it installs the other two.</td>
</tr>
<tr>
<td width="76" align="center"><a href="https://github.com/crimsondevil0929/interlock"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/interlock-dark.svg"><img src="assets/interlock.svg" width="48" height="48" alt="Interlock"></picture></a></td>
<td><a href="https://github.com/crimsondevil0929/interlock"><b>Interlock</b></a> &nbsp;<code>interlock-escrow</code><br>
Stage what an AI agent's write does, measure it, and commit it once or not at all.</td>
</tr>
<tr>
<td width="76" align="center"><a href="https://github.com/crimsondevil0929/agentgov"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/agentgov-dark.svg"><img src="assets/agentgov.svg" width="48" height="48" alt="AgentGov"></picture></a></td>
<td><a href="https://github.com/crimsondevil0929/agentgov"><b>AgentGov</b></a> &nbsp;<code>interlock-agentgov</code><br>
Spend and rate limits for a whole tree of AI agents, held before a call and settled after.</td>
</tr>
</table>

**See it working:** [crimsondevil0929.github.io/fiduciary](https://crimsondevil0929.github.io/fiduciary/).
Eight agent workflows on six kinds of system, a real model's recorded turns replayed on the
current release, and audit bundles you can verify in your browser.

**Try it on one tool,** in shadow mode, where nothing is refused and everything that would
have been is reported:

```bash
pip install interlock-fiduciary
fiduciary init --solo --shadow --substrate sqlite --database app.db
```
