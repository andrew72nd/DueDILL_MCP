# 🤖 Instructing VS Code Copilot Chat with Local Ollama Models

This guide details how to configure and run the **DueDill MCP Server** locally inside VS Code using the **GitHub Copilot Chat** extension paired with local **Ollama** models.

---

## 📋 Prerequisites

1. **Ollama Installed & Running**:
   - Download Ollama from [ollama.com](https://ollama.com).
   - Ensure the Ollama service is active (run `ollama list` in your terminal to verify).

2. **Tool-Calling Local Model**:
   - To use MCP tools, the local model **must support tool/function calling**.
   - Download a recommended model:
     ```bash
     ollama pull qwen2.5-coder:14b
     # OR
     ollama pull gemma4:12b
     # OR
     ollama pull llama3.1:8b
     ```
   - *Note*: Standard models without function-calling capabilities (e.g., base llama3 or older codegen models) will not understand how to invoke MCP tools.

3. **VS Code & Copilot Setup**:
   - Make sure you are using a modern version of VS Code (v1.99+).
   - Install **GitHub Copilot** and **GitHub Copilot Chat** extensions.
   - Sign in to your GitHub account.

---

## ⚙️ Configuration

VS Code discovers MCP servers via a configuration file (`mcp.json`). You can set this up at the workspace level for this project.

1. In the root of your workspace (`DueDILL_MCP`), create a folder named `.vscode`.
2. Inside `.vscode`, create a file named `mcp.json` with the following content:

```json
{
  "servers": {
    "duedill-mcp": {
      "command": "node",
      "args": ["e:/Qsync/_github/andrew72nd/DueDILL_MCP/index.js"]
    }
  }
}
```
*(Note: If you have moved the repository, update the absolute path to `index.js` accordingly. Use forward slashes `/` on Windows.)*

3. Reload VS Code or execute the command **`MCP: Reset Cached Tools`** from the VS Code Command Palette (`Ctrl+Shift+P`).
4. To check if the server is active, open the Command Palette and select **`MCP: List Servers`**. You should see `duedill-mcp` listed as **Connected**.

### 🤖 Workspace Agent Auto-Installation (With Warnings)

> [!WARNING]
> **VS Code Copilot Chat Sandboxing**: Standard VS Code Copilot Chat sessions (especially when configured with local Ollama models) are strictly sandboxed. They **cannot** execute background terminal commands (like `git clone` or `npm install`) or edit configuration files directly.
> 
> You should only use the agent prompt below if you are using a workspace editor agent with active filesystem and command-execution capabilities (such as Cursor Composer, Windsurf, or Antigravity) that requests your approval to run commands and write files.

If you are using a capable workspace agent, you can copy-paste this prompt to guide it through the setup:

> "Please install and configure the DueDill MCP server in my workspace: clone the repository `https://github.com/andrew72nd/DueDILL_MCP` into a `DueDILL_MCP` subdirectory, run `npm install` inside that folder to set up dependencies, create a `.vscode/mcp.json` file in my workspace root pointing to the absolute path of the cloned `index.js` (ensuring forward slashes are used for the Windows path), and verify the server boots successfully by running it briefly."

---

## ⚡ The Single-Prompt Autonomous Instruction

When using **Copilot Chat**, enable **Agent mode** (the toggle switch in the Copilot Chat pane, or type `@copilot` if active).

Simply copy and paste the following prompt to begin the complete automated due diligence flow:

```text
duedill AAPL
```

### 🧠 What the Agent Will Do:
Upon receiving this single instruction, the agent will:
1. **Initialize**: Call `list_gates` to read the due diligence framework and weights.
2. **Execute Gates 1-5**:
   - Fetch the prompt for each gate using `get_gate_prompt`.
   - Use search tools or workspace context to research the target company (e.g., revenue growth, margins, capital allocation, moat durability).
   - Draft a markdown analysis section for each gate.
   - Call `parse_gate_response` to extract numerical scores and core arguments.
3. **Compile**:
   - Fetch the final synthesis prompt.
   - Generate the investment thesis and key risks.
   - Call `compile_final_report` to generate the complete, ready-to-use executive dossier.

---

## 🛠️ Troubleshooting

- **Agent doesn't trigger tools**: Ensure you have selected a tool-calling model (like `qwen2.5-coder`) in the Copilot chat dropdown, and that **Agent mode** is toggled on.
- **Path errors**: Double-check the absolute path in `.vscode/mcp.json`. Path backslashes (`\`) on Windows must be converted to forward slashes (`/`).
- **Connection issues**: Check the VS Code Output panel. Select **MCP** from the dropdown on the top right to view logs from the server.
