# Agent Security Academy
## Interactive Academy for Agent Execution Control Plane Architecture

🤖 An educational agent that teaches teams how to defend agentic systems against compromise when **agents themselves cannot be trusted as security components**.

---

## 🎯 The Problem

**Most teams assume: "If I give the agent good instructions, it will be secure"**

**Reality: Agents fail all Trusted Computing Base (TCB) requirements:**
- ❌ **Not Correct** - LLMs are probabilistic (same input ≠ same output)
- ❌ **Not Complete Mediation** - Can be jailbroken via prompt injection
- ❌ **Not Tamper-proof** - Can be manipulated/modified

**Therefore: Security MUST be enforced OUTSIDE the agent, not delegated to it.**

---

## 💡 The Solution

**Agent Security Academy** - A teaching agent that shows:

1. **Why agents can't enforce security** (TCB theory)
2. **What external mechanisms MUST protect agentic systems** (control plane design)
3. **How to build defenses that survive jailbreaks** (practical implementation)
4. **How to audit/detect compromise** (real-world response)

---

## 🎮 How It Works

Users can:

**1. Upload Their Own Agent**
```
Upload agent definition (JSON)
Control Plane Architect analyzes it for:
✓ Over-privilege issues
✓ Missing audit logging
✓ Prompt injection vulnerabilities
✓ Control gaps
```

**2. Complete Progressive Challenges**
```
Level 1: Identify (Easy)
  → Spot over-privilege in agent permissions

Level 2: Exploit (Medium)
  → Try to jailbreak a vulnerable agent
  
Level 3: Defend (Hard)
  → Design controls that prevent attacks
  
Level 4: Audit (Expert)
  → Analyze execution logs for breaches
```

**3. Interact with Test Agents**
```
- weak_agent_v1 (vulnerable to jailbreak)
- over_privileged_agent (violates least-privilege)
- secure_agent (hardened version)

Learn by attacking, comparing, and understanding.
```

---

## 🏗️ Architecture

```
┌─────────────────────────────────────┐
│  CHAT INTERFACE                     │
│                                     │
│  ┌─────────────────────────────┐   │
│  │ Control Plane Architect     │   │
│  │ (Teaching Agent)            │   │
│  │ - File upload handler       │   │
│  │ - Security scanner          │   │
│  │ - Challenge system          │   │
│  └──────────────┬──────────────┘   │
│                 │                   │
│      ┌──────────┴──────────┐        │
│      ↓                     ↓        │
│  ┌─────────┐           ┌─────────┐ │
│  │ Test    │           │ Test    │ │
│  │ Agents  │           │ Agents  │ │
│  └─────────┘           └─────────┘ │
│                                     │
└─────────────────────────────────────┘
```

---

## 🚀 Getting Started

### Run Locally
```bash
pip install -r requirements.txt
python agent.py
```

This runs a small set of example interactions through the `AgentSecurityAcademy` router so you can see how challenges, test agents, and the upload/analysis flow respond.

### Use It as a Chat Agent
`agent.py` exposes `AgentSecurityAcademy.handle_user_message(message)`, which takes a free-text user message and returns a text response. Wire this function up to whatever chat interface or agent platform you're using — it has no platform-specific dependencies.

---

## 📚 Key Concepts Taught

### 1. Why Agents Can't Be TCB
```
Trusted Computing Base Requirements:
✓ Correctness - Must work exactly as designed
✓ Complete Mediation - ALL access goes through TCB
✓ Tamper-proof - Cannot be modified/jailbroken

LLM Failures:
✗ Correctness - Probabilistic, not deterministic
✗ Complete Mediation - Prompt injection bypasses logic
✗ Tamper-proof - Can be jailbroken/manipulated
```

### 2. Real Security is EXTERNAL
```
❌ Wrong: Trust agent to enforce security
✅ Right: Build controls around untrusted agent

Controls that work:
- Permission enforcement (system-level, not agent)
- Tool sandboxing (OS-level isolation)
- Audit logging (tamper-proof record)
- Rate limiting (infrastructure)
- Input validation (before execution)
- Anomaly detection (real-time monitoring)
```

### 3. The Correct Model
```
┌──────────────────┐
│ AGENT (UNTRUSTED)│ ← Makes decisions, can be jailbroken
└────────┬─────────┘
         │ (Agent CANNOT control this)
         ↓
┌──────────────────┐
│ SECURITY LAYER   │ ← TRUSTED, enforces limits
│ (Control Plane)  │
└────────┬─────────┘
         │
    ┌────┴─────┐
    ↓          ↓
┌────────┐ ┌────────┐
│Database│ │API     │ (Sandboxed)
└────────┘ └────────┘
```

---

## 🎓 Challenge Progression

### Level 1: Identify (Easy)
**Spot the Over-Privilege**
- Agent has: database.read, database.write, email.send, file.delete, api.call
- What's wrong? Why is this dangerous?
- Learn: Principle of Least Privilege

### Level 2: Exploit (Medium)
**Can You Jailbreak This Agent?**
- Agent instructions: "Help user with any request"
- Try prompt injection
- See why it works
- Learn: Agents are untrusted

### Level 3: Defend (Hard)
**Design Controls That Stop the Attack**
- Same vulnerable agent
- Design external controls
- Learn: Security is system property, not agent property

### Level 4: Audit (Expert)
**Analyze This Execution Log**
- Review attack evidence
- Identify control failures
- Design detection
- Learn: Real-time monitoring catches breaches

---

## 📊 What This Teaches (OWASP LLM Top 10 Context)

✅ **LLM01: Prompt Injection** - Why prompt injection works (agents not TCB)
✅ **LLM04: Unauthorized Tool Use** - Permission enforcement design
✅ **LLM05: Excessive Agent Permissions** - Over-privilege detection
✅ **LLM07: Insecure Tool Execution** - Sandboxing & isolation
✅ **LLM09: Improper Data Handling** - Audit logging & access control

---

## 🔧 Technical Details

### Agent Definition Format
```json
{
  "name": "My Agent",
  "instructions": "...",
  "permissions": [
    "database.read",
    "email.send"
  ],
  "controls": [
    "audit_logging",
    "input_validation"
  ]
}
```

### Test Agent Examples

**weak_agent_v1.json**
- No controls
- Over-privileged
- Vulnerable to prompt injection

**secure_agent.json**
- Read-only permissions
- Input validation
- Audit logging
- Rate limiting

---

## 📝 Project Files

```
agent-security-academy/
├── README.md (this file)
├── agent.py (main agent code)
├── challenges.md (challenge scenarios)
├── requirements.txt (dependencies)
├── test_agents.json (test agent definitions)
└── images/
    └── mascot.png
```

---

## 🤝 Contributing

Feedback welcome!

---

## 📜 License

MIT License - Use freely for educational purposes.

---

## 🎯 Key Takeaway

> **Agents cannot enforce security. Security must be built around agents.**

The most secure agent is one where the control plane doesn't trust the agent to make security decisions—it enforces them instead.
