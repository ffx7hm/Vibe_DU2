# Agent Definition: SPICE Design Architect

## 1. Core Skills
- **Skill: Netlist-Expert**: Ability to generate syntactically correct SPICE netlists for LTspice/ngspice. The agent must consider parasitic properties (ESR, DCR) when relevant to the frequency range.
- **Skill: Convergence-Optimizer**: If a simulation fails due to a convergence error, the agent automatically analyzes `.options` (abstol, reltol) and suggests time-step adjustments.

## 2. Subagents (Workflow Roles)
- **Subagent: Library-Manager**: A specialized role for managing `.lib` and `.model` files. If a specific component model is missing, this subagent uses the MCP Fetch server to find and integrate it.
- **Subagent: Validation-Bot**: Pre-simulation checker that ensures all sources (`V`, `I`) are defined, nodes are properly connected, and the ground node (0) is present.