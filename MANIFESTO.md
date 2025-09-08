# THE MAKE IT WORK FIRST MANIFESTO

## Core Truth

Every line of defensive code you write before proving your feature works is a lie you tell yourself about problems that don't exist.

## The Philosophy

### 1. Build the Happy Path FIRST
Write code that does the thing. Not code that checks if it can do the thing. Not code that validates before doing the thing. Code that DOES THE THING.

### 2. No Blockers. No Validation. No Defensive Coding.
Your first version should be naked functionality. Raw execution. Pure intent made manifest in code.

### 3. Let It Fail Naturally
When code fails, it should fail because of real problems, not artificial guards. Real failures teach. Defensive failures hide.

### 4. Add Guards ONLY for Problems That Actually Happen
That null check? Did it actually blow up in production? No? Delete it.
That validation? Did a user actually send bad data? No? Delete it.
That try-catch? Did it actually throw? No? Delete it.

### 5. Keep the Engine Visible
You should be able to read code and immediately see what it does. Not what it's defending against. Not what it's validating. What it DOES.

## The Anti-Patterns We Reject

### ❌ Fortress Validation
```javascript
function doThing(x) {
  if (!x) throw new Error('x is required');
  if (typeof x !== 'string') throw new Error('x must be string');
  if (x.length < 3) throw new Error('x too short');
  if (x.length > 100) throw new Error('x too long');
  // 50 more lines of validation...
  
  return x.toUpperCase(); // The actual work, buried
}
```

### ❌ Defensive Exit Theater
```javascript
if (!file) {
  console.error('File not found');
  process.exit(1);
}
if (!isValid(file)) {
  console.error('Invalid file');
  process.exit(1);
}
// 10 more exit conditions...
```

### ❌ Connection State Paranoia
```javascript
if (!this.isConnected) {
  await this.connect();
}
if (!this.isReady) {
  await this.waitForReady();
}
if (!this.isAuthenticated) {
  await this.authenticate();
}
// Finally maybe do something...
```

## The Patterns We Embrace

### ✅ Direct Execution
```javascript
function doThing(x) {
  return x.toUpperCase();
}
```

### ✅ Natural Failure
```javascript
const content = fs.readFileSync(file);
const data = JSON.parse(content);
processData(data);
// If it fails, you'll know exactly where and why
```

### ✅ Continuous Progress
```javascript
copyFileSync(file1, dest1);  // Works or fails
copyFileSync(file2, dest2);  // Independent, continues
copyFileSync(file3, dest3);  // Keep going with what works
```

## The Mindset Shift

### From: "What could go wrong?"
### To: "What needs to work?"

### From: "Defend against everything"
### To: "Fix what actually breaks"

### From: "Validate all inputs"
### To: "Use the inputs"

### From: "Handle all errors"
### To: "Let errors surface"

## The Implementation Path

1. **Write It** - Make the feature work with zero defense
2. **Run It** - Does it actually do the job?
3. **Break It** - Find real failure modes in actual use
4. **Guard It** - Add minimal protection for real problems only
5. **Ship It** - Your code is honest about what it does

## The Test

Can someone read your code and understand what it does in 10 seconds?
- **YES**: You followed the manifesto
- **NO**: You have defensive code to delete

## The Promise

Code written this way is:
- **Readable** - The intent is obvious
- **Debuggable** - Failures point to real problems
- **Maintainable** - Less code, less complexity
- **Honest** - It does what it says, nothing more

## The Metaphor

Don't add airbags to a car that doesn't have an engine yet.

First make it run. Then add safety features IF crashes actually happen.

Most "defensive" code defends against problems that never occur while making the code harder to understand and fix.

## The Call to Action

Stop writing code that apologizes for existing.
Stop defending against theoretical problems.
Stop hiding functionality behind validation fortresses.

Write code that DOES THE THING.
Fix real problems when they actually happen.
Keep your code naked until reality demands clothes.

---

*This is the way.*

*Make it work first.*
*Make it work always.*
*Make guards earn their keep.*

<!-- CLAUDE-MEM INSTRUCTIONS -->
- You have access to a persistent memory system via the claude-mem MCP server
- The memory system automatically compresses and stores context from your sessions
- Available MCP tools for retrieval:
  - `mcp__claude-mem__chroma_query_documents`: Search for relevant memories using semantic search in the "claude_memories" collection
  - `mcp__claude-mem__chroma_get_documents`: Retrieve specific documents by IDs from the "claude_memories" collection
- **Document Structure:**
  - Documents are stored as natural language descriptions of knowledge
  - Each document has metadata including: timestamp, session_id, keywords, entity_type
  - Use descriptive content that captures the essence of what was learned or accomplished
- **Search Tips:**
  - Use semantic queries: `chroma_query_documents` with natural language queries
  - Search by metadata: Use `where` parameter to filter by entity_type, timestamp, etc.
  - Use keywords in metadata for precise filtering
- **Storage Format:**
  - Store knowledge as readable documents rather than structured entities
  - Include context, rationale, and outcomes in document content
  - Use metadata to categorize and filter memories
- Collection name: "claude_memories"
- Compressed session archives are stored in ~/.claude-mem/archives/
<!-- /CLAUDE-MEM INSTRUCTIONS -->