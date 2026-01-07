# AI4PKM Vault Configuration

This directory contains the AI4PKM vault configuration for YUjinEDU.

## Configuration Summary

### Executor Settings
- **Default Executor**: `gemini_cli`
- **EIC Agent Executor**: `codex_cli` (for file modification tasks)

### Directory Structure
1. `orchestrator.yaml` - Main configuration with Gemini CLI as default executor
2. EIC (Enrich Ingested Content) agent configured to use Codex CLI
3. Set up required directory structure:
   - `_Settings_/Prompts/` - Agent prompt definitions
   - `_Settings_/Tasks/` - Task tracking files (auto-created)
   - `_Settings_/Logs/` - Execution logs (auto-created)
   - `_Settings_/Skills/` - Skills library
   - `_Settings_/Bases/` - Knowledge bases
   - `Ingest/Clippings/` - Input directory for web clippings
   - `AI/Articles/` - Output directory for processed content

### Agents Configured
- **Enrich Ingested Content (EIC)**
  - Input: `Ingest/Clippings`
  - Output: `AI/Articles`
  - Executor: `codex_cli`
  - Purpose: Process web clippings and ingested content

### Pollers
All pollers are currently disabled:
- Apple Photos
- Apple Notes
- Gobi
- Gobi by Tags
- Limitless

## Usage

### Test Configuration
```bash
# Navigate to vault directory
cd ai4pkm_vault

# Show configuration
ai4pkm --show-config

# Check orchestrator status
ai4pkm --orchestrator-status

# Test with simple prompt
ai4pkm -p "Hello Gemini, introduce yourself"

# Start orchestrator
ai4pkm --orchestrator
```

## References
- [Orchestrator Documentation](../docs/orchestrator.md)
- [CLI Tool Documentation](../docs/cli_tool.md)
