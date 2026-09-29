# Deployment Guide
## Getting Agent Execution Control Plane Live on Guild.ai

---

## 🚀 Quick Start (5 minutes)

### Step 1: Prepare GitHub Repository
```bash
# You should already have this repo set up with:
# - agent.py
# - README.md
# - challenges.md
# - test_agents.json
# - requirements.txt

# If not, push to GitHub:
git add .
git commit -m "Initial commit: Agent Execution Control Plane"
git push origin main
```

### Step 2: Create Guild.ai Account
1. Go to [guild.ai](https://guild.ai)
2. Click "Sign Up"
3. Use GitHub or email
4. Create account

### Step 3: Create Workspace
1. In Guild.ai, click "Create Workspace"
2. Name: "Agent Security Academy"
3. Description: "Teaching control plane architecture for agent security"
4. Click create

### Step 4: Import from GitHub
1. In your workspace, click "Import from GitHub"
2. Authorize Guild.ai to access your GitHub
3. Select: `your-username/agent-security-academy`
4. Click import
5. **Guild automatically deploys!**

### Step 5: Get Your Link
Once deployed, Guild gives you a workspace link:
```
https://guild.ai/workspace/agent-security-academy
```

Share this link with judges and users. That's your entry point.

---

## 🔧 Local Testing (Optional)

### Test Agent Locally Before Deploying
```bash
# 1. Clone your repo
git clone https://github.com/your-username/agent-security-academy
cd agent-security-academy

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the agent
python agent.py
```

Expected output:
```
============================================================
Agent Execution Control Plane - Example Interactions
============================================================

User: What is this about?

Agent: 🔐 Agent Execution Control Plane
...
```

---

## 📋 What Guild.ai Handles

✅ **Hosting** - Your agent runs on Guild's servers
✅ **Web UI** - Users interact through chat interface
✅ **File Upload** - Users can upload agents for analysis
✅ **Logging** - All interactions are logged
✅ **Scaling** - Handles multiple users
✅ **AI Integration** - Uses Claude for agent logic
✅ **Deployment** - No manual deployment needed

---

## 🎯 How Users Access Your Agent

1. **Open Guild.ai workspace link**
   ```
   https://guild.ai/workspace/agent-security-academy
   ```

2. **See your agent**
   ```
   Control Plane Architect
   (Your main teaching agent)
   ```

3. **Start chatting**
   ```
   User: "Show me a challenge"
   Agent: "Choose a level..."
   ```

4. **Upload their own agents**
   ```
   User uploads: my_agent.json
   Agent analyzes: "Found 3 vulnerabilities..."
   ```

---

## 🔄 Updating Your Agent

After deployment, if you want to make changes:

### Update Option 1: Push to GitHub (Recommended)
```bash
# Make changes to agent.py
vim agent.py

# Push to GitHub
git add agent.py
git commit -m "Fix: Improve challenge descriptions"
git push origin main

# Guild automatically redeploys from GitHub
# Changes live in ~2 minutes
```

### Update Option 2: Edit in Guild.ai UI
1. Go to your workspace
2. Click "Edit Agent"
3. Modify agent instructions
4. Click "Save"
5. Changes live immediately

---

## 📊 Monitoring Your Agent

Guild.ai provides:
- **Usage logs** - See how many users interacted
- **Interaction history** - Read conversations
- **Error logs** - Debug any issues
- **Analytics** - Usage patterns, popular features

Access in Guild workspace → Settings → Analytics

---

## 🚨 Troubleshooting

### Issue: Import from GitHub fails
**Fix:**
1. Make sure repo is public
2. Check GitHub authorization
3. Ensure `README.md` exists
4. Try again

### Issue: Agent not responding
**Fix:**
1. Check Guild status page
2. Verify GitHub repo has latest code
3. Try a manual redeploy

### Issue: Users can't upload files
**Fix:**
Guild automatically enables file upload. No configuration needed.
If it doesn't work:
1. Check user's browser
2. Try different file format
3. Check file size (should be < 10MB)

---

## 🎥 Recording Your Demo

Once agent is live on Guild.ai:

### Demo Checklist
- [ ] Open Guild.ai workspace link
- [ ] Show the Control Plane Architect agent
- [ ] Chat with it (ask for challenge)
- [ ] Upload a test agent (or use provided weak_agent_v1.json)
- [ ] Show the security analysis
- [ ] Complete a challenge
- [ ] Explain the lesson

### Recording Tips
```
Screen recorder: Mac Command+Shift+5, Windows Windows+Shift+S
Duration: 90 seconds
Narration: Explain what you're showing (no dead air)
Quality: 720p minimum, MP4 format
Upload: YouTube (unlisted), Vimeo, or similar
Share: Get the link for hackathon submission
```

### Demo Script (90 seconds)
```
0-10s: "Agents get jailbroken. Here's why."
       [Show weak_agent_v1 being attacked]

10-25s: "Without controls, attacks succeed."
        [Show jailbreak working]

25-40s: "With proper controls, attacks fail."
        [Show secure_agent rejecting attack]

40-70s: "Guild.ai hosts an interactive academy that teaches
         how to defend against this."
        [Show uploading custom agent]
        [Show analysis results]
        [Show challenge system]

70-90s: "Learn control plane architecture.
         Build secure agents."
        [Show guild.ai link]
        [End screen with repo/video links]
```

---

## 📝 Submission Checklist

Before hackathon submission:

- [ ] GitHub repo is public
- [ ] Agent is live on Guild.ai
- [ ] `README.md` explains the project
- [ ] `agent.py` is clean and documented
- [ ] `challenges.md` has all 4 levels
- [ ] `test_agents.json` has 3 examples
- [ ] Demo video is recorded (90 seconds)
- [ ] Demo video is uploaded (YouTube/Vimeo)
- [ ] All links are working

**Submit:**
1. GitHub repo URL
2. Guild.ai workspace URL
3. Demo video URL

---

## 🏆 What Judges See

**They will:**
1. ✅ Read your README.md
2. ✅ Review your agent.py code
3. ✅ Visit your Guild.ai workspace
4. ✅ Interact with the agent
5. ✅ Watch your demo video
6. ✅ Run Snyk scan on your code
7. ✅ Score you on the rubric

**Make sure:**
- ✅ Code is clean and well-documented
- ✅ Agent is responsive and helpful
- ✅ Challenges are clear and educational
- ✅ Demo clearly shows the value
- ✅ Guild.ai integration is meaningful (not just hosting)

---

## 🎓 Expected Guild.ai User Journey

```
1. User visits: guild.ai/workspace/agent-security-academy

2. Sees: Control Plane Architect agent

3. Options:
   a) "Show me a challenge" → Level 1 quiz
   b) "Analyze my agent" → Upload agent.json
   c) "Show test agents" → See weak/secure examples
   d) "Teach me about TCB" → Get educational content

4. User completes challenge:
   - Gets hints if stuck
   - Receives feedback on answer
   - Learns security lesson
   - Moves to next level

5. User uploads their agent:
   - Agent analyzes for vulnerabilities
   - Gets specific recommendations
   - Learns what to fix

6. User explores test agents:
   - Interacts with weak_agent_v1
   - Sees how to jailbreak it
   - Compares with secure_agent
   - Understands why controls matter
```

---

## 🔐 Security Note

Your agent on Guild.ai:
- **Does not** have access to real databases
- **Does not** store user data (beyond conversation logs)
- **Does not** execute real attacks
- **Only** teaches security concepts through examples

This is safe for demonstration and learning.

---

## 📞 Support

If issues during deployment:
1. Check Guild.ai status page
2. Review GitHub commit history
3. Test locally: `python agent.py`
4. Reach out to Guild.ai support

Good luck! 🎉
