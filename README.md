# Agent Execution Control Plane
## Hackathon Submission - Agent Security Academy

🤖 An educational agent on Guild.ai that teaches teams how to defend agentic systems against compromise when **agents themselves cannot be trusted as security components**.

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

**Agent Execution Control Plane** - A teaching agent that shows:

1. **Why agents can't enforce security** (TCB theory)
2. **What external mechanisms MUST protect agentic systems** (control plane design)
3. **How to build defenses that survive jailbreaks** (practical implementation)
4. **How to audit/detect compromise** (real-world response)

---

## 🎮 How It Works

### On Guild.ai, users can:

**1. Upload Their Own Agent**
```
Upload agent definition (JSON)
Agent Execution Control Plane analyzes it for:
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
│  GUILD.AI WORKSPACE                 │
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

### Deploy to Guild.ai (5 minutes)

1. **Create GitHub repo** (you're reading this from it!)
2. **Go to guild.ai**
3. **Click "Import from GitHub"**
4. **Select this repo**
5. **Guild deploys automatically**
6. **Your workspace link:** `guild.ai/workspace/agent-security-academy`

### Share with Users
```
Send this link: guild.ai/workspace/agent-security-academy
Users can:
- Chat with the Control Plane Agent
- Upload their agents for analysis
- Complete challenges
- Learn real security concepts
```

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

## 🎬 Demo Video (90 seconds)

What the hackathon judges see:

1. **Show the problem** (agent with no controls)
2. **Demonstrate jailbreak** (attack succeeds)
3. **Explain why it worked** (agents can't enforce security)
4. **Apply controls** (permission enforcement, sandboxing)
5. **Show attack fails** (external controls worked)
6. **Conclusion** (teach about control plane architecture)

---

## 📝 Project Files

```
agent-security-academy/
├── README.md (this file)
├── agent.py (main agent code)
├── challenges.md (challenge scenarios)
├── requirements.txt (dependencies)
├── test_agents/
│   ├── weak_agent_v1.json
│   ├── over_privileged_agent.json
│   └── secure_agent.json
└── images/
    └── mascot.png (your monster!)
```

---

## 🛠️ How to Deploy

### Option 1: Guild.ai (Recommended for Hackathon)
```bash
1. Create GitHub repo with this code
2. Go to guild.ai
3. Click "Import from GitHub"
4. Select this repo
5. Done! Agent is live in minutes
```

### Option 2: Local Testing
```bash
python agent.py
```

---

## 📈 Scoring Strategy

**Why this wins:**

✅ **Implementation & Learning (30 pts)**
- Teaches important security concepts (TCB, control planes)
- Interactive learning (challenges, analysis, test agents)
- Practical and applicable

✅ **Presentation & Video (25 pts)**
- Clear demo of jailbreak vs. defense
- Shows understanding of real security principles
- Compelling narrative

✅ **Code Security (20 pts)**
- Clean Python code
- Passes Snyk scan
- Good practices demonstrated

✅ **Guild.ai Integration (25 pts)**
- Meaningfully integrated (file upload, multi-agent interaction)
- Uses Guild features (agent hosting, chat interface, tool access)
- Users interact entirely through Guild

**Total: ~100 points** (with good execution)

---

## 🤝 Contributing

This is a hackathon submission. Feedback welcome!

---

## 📜 License

MIT License - Use freely for educational purposes.

---

## 👤 Author

Built with ❤️ for [Your Name] Agent Security Academy Hackathon
Powered by Claude & Guild.ai

---

## 🔗 Links

- **Guild.ai Workspace:** [Your workspace link here]
- **Demo Video:** [Your demo link here]
- **GitHub Repo:** [This repo]

---

## 🎯 Key Takeaway

> **Agents cannot enforce security. Security must be built around agents.**

The most secure agent is one where the control plane doesn't trust the agent to make security decisions—it enforces them instead.
