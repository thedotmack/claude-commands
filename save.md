Write an overview of the current conversation context and:
1. Add it to claude-mem using the chroma MCP tools
2. Append an overview entry to ~/.claude-mem/claude-mem-index.jsonl with:
   - Use the current working directory name as the project (use Bash `basename $(pwd)`)
   - Generate a descriptive session_id based on the main topic discussed
   - Use the current timestamp (use Bash `date -u +"%Y-%m-%dT%H:%M:%S.000Z"`)
   - Format: {"type":"overview","content":"[concise paragraph summary]","session_id":"[topic-based-id]","project":"[from pwd]","timestamp":"[current UTC time]"}
   - Example: echo '{"type":"overview","content":"...","session_id":"import-history-redesign","project":"'$(basename $(pwd))'","timestamp":"'$(date -u +"%Y-%m-%dT%H:%M:%S.000Z")'"}' >> ~/.claude-mem/claude-mem-index.jsonl