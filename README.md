# Homework: AI Coding Agent Setup (SPICE Simulation Workflow)

This project demonstrates the configuration of an autonomous coding agent (using the **Claude Code** interface) tailored for electronic circuit design and SPICE simulation automation.

## About this Setup
I work in the field of **microelectronics**, where circuit simulations are a core part of my daily workflow. For this assignment, I decided to leverage my domain expertise and "re-use" a real-world scenario. Instead of a generic coding assistant, I have configured this agent to act as a **SPICE Simulation Specialist**, streamlining the process of netlist generation and validation.

## Architecture
In accordance with the assignment requirements, this setup **does not use Plugins or Marketplace extensions**. All functionality is built natively on the **Model Context Protocol (MCP)**.

### 1. Configured MCP Servers
- **Filesystem Server**: Bridges the agent to the local workspace containing `.sp` netlists and library files.
- **Fetch Server**: Enables the agent to retrieve real-time technical data and component models from external web sources (e.g., TI, Analog Devices).

### 2. Skills and Custom Instructions
The agent is equipped with domain-specific expertise for electrical engineering (see `custom_instructions.md`). This allows for the generation of optimized netlists and simulation directives rather than generic code.

### 3. Subagents
The workflow is divided between specialized subagents (**Library-Manager** and **Validation-Bot**) that ensure simulation integrity before execution.

## How to Run
1. Copy the configuration from `claude_desktop_config.json` into your local Claude Desktop config file.
2. Initialize the agent in your terminal using:
   `npx @anthropic-ai/claude-code`