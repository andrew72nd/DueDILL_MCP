# DueDill Model Context Protocol (MCP) Server

The **DueDill MCP Server** is a self-contained local tool suite that connects LLM agents directly to the **DueDill** investment due diligence framework. 

By running this server in your agent environment (such as **VS Code GitHub Copilot Chat**, **Cursor**, or **Claude Desktop**), local models (like **Ollama**'s `qwen2.5-coder` or `llama3.1`) can autonomously fetch normalized prompts, parse ratings and key evidence out of analyses, and compile formatted Markdown investment reports optimized for **Affine** import.

---

## What It Does

This MCP server replicates the exact logic, regex parsers, and templates used by the DueDill Next.js web application. It exposes four core tools to your AI agent:

1.  **`list_gates`**
    *   **Description**: Retrieves the checklist of all due diligence gates/pillars, their weight coefficients, and purposes from `manifest.json`.
2.  **`get_gate_prompt`**
    *   **Description**: Reads a specific pillar prompt from the file system, prepends the core analysis rules from `00-core-principles.md`, and interpolates `{COMPANY}` and `{DATE}` tokens dynamically.
3.  **`parse_gate_response`**
    *   **Description**: Analyzes raw markdown outputs from the model to automatically parse out the numerical **Rating Score** (0-100), the **PASS/FAIL** verdict, a list of **Key Evidence** bullets, the **Final Report Input** summary block, and **References** using strict RegExp patterns.
4.  **`compile_final_report`**
    *   **Description**: Aggregates ratings and summaries from the individual gates to compile a comprehensive, polished due diligence Markdown report suitable for investment committees and fully compatible with Affine's markdown parser.

---

## Prompt Asset Repository

The server includes the local self-contained prompts folder:
*   `prompts/manifest.json`: Configuration mapping files and weights.
*   `prompts/00-core-principles.md`: Global guidelines on source quality, formatting, and scepticism.
*   `prompts/gate-1-fundamental-quality-screen.md`: Checklist for basic balance sheet health.
*   `prompts/gate-2-rule-of-40.md`: Evaluates growth and FCF efficiency.
*   `prompts/gate-3-moat-test.md`: Chinese reverse-engineering moat durability stress test.
*   `prompts/gate-4-ceo-filter.md`: Leadership capital allocation evaluation.
*   `prompts/gate-5-valuation.md`: Conservative DCF scenario and sensitivity modeling.
*   `prompts/final-report-compiler.md`: The template instructions used to synthesize summaries into the final executive recommendations.

---

## Installation & Setup

1.  Ensure you have **Node.js** (v18+) installed.
2.  Navigate to the `DueDILL_MCP` folder:
    ```bash
    cd DueDILL_MCP
    ```
3.  Install dependencies:
    ```bash
    npm install
    ```

---

## How to Configure in VS Code for Local Agents

VS Code (v1.99+) natively supports Model Context Protocol servers in GitHub Copilot Chat when pointing to local models.

### 1. Requirements
*   **Ollama**: Installed and running locally.
*   **Tool-Calling Model**: You **MUST** run a model that supports native function/tool calling, such as:
    *   `qwen2.5-coder` (e.g. `qwen2.5-coder:14b` or `7b`)
    *   `llama3.1` (8B+)
    *   `mistral-nemo`
    *   *Note*: Standard models without explicit tool-calling configurations cannot invoke MCP tools.

### 2. VS Code Configuration File (`mcp.json`)
You can register this MCP server either globally or for this workspace only.

#### Workspace-Level Configuration (Recommended)
1. Inside your project folder, create a `.vscode` directory if it doesn't exist.
2. Create a file named `mcp.json` (`.vscode/mcp.json`) and paste:

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
*(Always use forward slashes `/` for Windows folder paths to avoid JSON syntax errors)*.

#### Global User Configuration
1. Open the Command Palette (`Ctrl+Shift+P` or `Cmd+Shift+P`).
2. Search for and select: **`MCP: Open User Configuration`**.
3. Add the `duedill-mcp` configuration under the `servers` object.

### 3. Verification
1. Run the Command Palette command **`MCP: List Servers`** and confirm that `duedill-mcp` shows **Connected**.
2. Open the **Output Panel**, select **MCP** from the dropdown list on the right, and verify that the tools are discovered correctly.
3. If you edit prompt files or the index code, trigger **`MCP: Reset Cached Tools`** to force VS Code to reload tool schemas.

---

## Typical Agentic Workflow

When talking to your local agent in Copilot Chat (in **Agent** mode):

1.  **Select Company**:
    *   *Prompt*: `"I want to evaluate Palantir (PLTR). Start the DueDill analysis."`
2.  **Fetch Gate Prompts**:
    *   *Prompt*: `"Get the prompt for Gate 1."`
    *   *Action*: The agent calls `get_gate_prompt(gateId: 1, company: "Palantir (PLTR)")` and gets the fully interpolated prompt.
3.  **Perform Analysis**:
    *   *Prompt*: `"Answer this prompt using your training data, search, or local workspace context. Ensure you include the exact output structure."`
4.  **Parse Score & Reasons**:
    *   *Prompt*: `"Parse the Gate 1 response we just got."`
    *   *Action*: The agent calls `parse_gate_response` to verify that the rating and key evidence have been extracted correctly.
5.  **Repeat for Gates 2–5**.
6.  **Compile Executive Recommendation**:
    *   *Prompt*: `"Get the final report compiler prompt."`
    *   *Action*: Agent calls `get_gate_prompt(gateId: "final")` injecting the five gate summary inputs.
    *   *Prompt*: `"Generate the final report synthesis chapters."`
7.  **Generate Final Dossier**:
    *   *Prompt*: `"Compile the complete due diligence report."`
    *   *Action*: Agent calls `compile_final_report` mapping all summaries, ratings, and syntheses into a clean markdown dossier ready for Affine.
