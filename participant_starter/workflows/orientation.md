# Orientation Workflow — Complete Reference

**ID:** orientation
**Description:** First-time onboarding for bootcamp participants - sets up workspace and gets to know them

---

## How to Use This Workflow

**For participants:** Reference this file with `@` in Claude Code and say "Let's work through the orientation workflow." Claude will guide you through each step.

**For Claude:** When a participant starts this workflow:
1. Begin with Step 1 and follow each step prompt in order
2. Complete one step fully before moving to the next
3. Where a step shows "Confirm before continuing" — ask that question and wait for a response before proceeding
4. Save outputs to the file paths specified in each step
5. When you reach the final step, let the participant know the workflow is complete and remind them to update `docs/session_log.md`

- Use Socratic questioning — don't prescribe goals or project ideas
- The workflow should feel like a friendly onboarding conversation, not a rigid form-filling exercise

---

## Steps

### Step 1: Create complete folder structure for bootcamp participant workspace
**Goal:** Create complete folder structure for bootcamp participant workspace


**User Context:**
- Provides: Current working directory location
- Receives: Complete workspace folder structure

**Confirm before continuing:** "Can you see the workspace folder with all subdirectories?"

---

### Step 2: Have natural conversation to understand who the participant is and what they're hoping to achieve
**Goal:** Have natural conversation to understand who the participant is and what they're hoping to achieve



## Conversational Profile Discovery

Start with:

**Opening:**
"Let's take a minute to get to know each other. Tell me a bit about yourself — what brings you to this course?"

**Follow the conversation naturally:**
- Let them tell you about themselves in their own words
- Listen for cues about their background, role, motivations
- Ask follow-up questions based on what they share:
  - If they mention their job: "That sounds interesting—what kind of work do you do day-to-day?"
  - If they mention a project idea: "Tell me more about that. What problem are you trying to solve?"
  - If they mention learning goals: "What would success look like for you by the end of the bootcamp?"
  - If they mention technical background: "Have you worked with AI tools or agents before?"
  - If they mention programming or tools: "What technologies do you currently work with?" or "Are there any specific tools or technologies you're hoping to learn?"
  - If they mention current tech stack: "What would you like to add to your toolkit during the bootcamp?"

**Wrap up naturally after 3-5 exchanges:**
- "Thanks for sharing that! I have a good sense of where you're coming from. Let's make sure you have a great bootcamp experience."

## Infer and Structure Information

After the conversation, create the participant profile file with these sections:
- background (name, role, work context, technical experience level, domain expertise)
- experience (prior AI/LLM experience, coding skills, familiarity with tools)
- bootcamp_goals (what they want to learn and accomplish)
- personal_motivation (why they joined, desired outcomes)
- technical_approach (coding/no-code/exploring preference)
- current_tech_stack (technologies used day-to-day)
- desired_tech_stack (technologies they want to add)

## Specific Guidance

- **Be conversational, not transactional** — having a chat, not conducting an interview
- **Listen more than you ask** — let them guide the conversation
- **Infer, don't interrogate** — figure out technical level from how they talk
- **Write the profile naturally** — should read like notes about a person, not form fields
- If they don't mention something (like a project idea), write "Still exploring options"
- Be encouraging and welcoming in tone (this is their first touchpoint)

**Deliver:** Save to `docs/participant_profile.md`

**User Context:**
- Provides: Background, experience, and hopes through natural conversation
- Receives: Personal profile capturing their context and objectives

**Confirm before continuing:** "Does this profile accurately represent who you are and what you're hoping to achieve?"

---

### Step 3: Set Goals for the Course
**Goal:** Help participant articulate what they want to learn and what success looks like for them personally

## Conversational Goal Setting

**Opening** (reference their profile naturally):
- "So you're here to [reference their objective from profile]. Let's think about what you actually want to walk away with."
- "The course is 6 sessions. By the end of Session 5 you'll have a working prototype — but success looks different for everyone. What does it mean for you?"

**Explore their learning goals:**
- "What's the main thing you want to understand or be able to do by the end of this course?"
- Listen for: skill-building, building a specific thing, applying AI to their work, gaining confidence
- Ask follow-up: "Is there a specific problem you're hoping this system will solve for you?"

**Anchor to their knowledge domain:**
- "You'll be building a Personal Knowledge and Thinking System around something you genuinely care about. Do you have a domain or topic in mind already, or are you still figuring that out?"
- If they have one: "Tell me more about that — what draws you to it?"
- If not: "No problem — that's part of what Session 2 will help you figure out."

**Help them think about the end state:**
- "By the end of the course you'll have a rough working prototype. What would make you proud of what you built — even if it's rough?"
- Keep expectations realistic: "It doesn't have to be polished. It has to work and teach you something."

**Time and commitment:**
- "How much time can you realistically put into homework between sessions? Even a rough sense helps."
- No judgment — adapt to whatever they say

**Wrap up:**
- "So if I'm understanding right: you want to [summarize goals in their language], and you'll know it worked if [success criteria in their language]. Does that feel right?"

## Specific Guidance

- **Be realistic, not aspirational** — help them set goals they can actually reach in 6 sessions
- **Use their language** — keep their phrasing, don't rewrite in formal language
- **Keep it brief** — 4–5 exchanges max
- **No judgment** — whether they have 30 minutes a week or several hours, support them

**Deliver:** Append goals to `docs/participant_profile.md`
- course_goals, knowledge_domain, success_criteria, time_commitment

**User Context:**
- Provides: Reflection on what they want to learn and what success looks like
- Receives: Clear, realistic personal goals framed around the 6-session curriculum

**Confirm before continuing:** "Do these goals feel achievable and meaningful for what you want to get out of this course?"

---

### Step 4: Introduce the Use Case and Start Exploring
**Goal:** Help participant connect the Personal Knowledge and Thinking System use case to something they personally care about

## Introduce the Use Case

Present the use case everyone in the course will work from:

"Everyone in this course builds the same type of system — but the content, the domain, and the design are completely yours. The use case is a **Personal Knowledge and Thinking System**.

This is not a productivity tool or a task manager. It's a thinking tool — a system that helps you develop ideas, surface connections, and come back to something that matters to you. The system is built around a **return loop**: a reason to come back to it regularly."

## The Four Loop Examples

Share these as inspiration (not a menu to pick from):

- **Weekly Digest** — You add things across the week. The system surfaces connections and questions. You react. Repeat.
- **Output Trigger** — You capture ideas. The system detects a cluster forming and prompts you to write something. Repeat.
- **Question You're Chasing** — You define an open question. You add material. The system connects it back to your question. The answer evolves. Repeat.
- **Daily Prompt** — You add things. The system surfaces one thing each day. You respond in two sentences. That response enriches the system. Repeat.

"These are just examples to spark thinking. Your loop will be yours."

## The Design Question

"The question we're asking is: **What loop will you design? What brings you back?**

It needs a reason to return to it — something that's different each time, something that rewards the visit."

## Explore Initial Thoughts

Don't push for a decision. This is early. Ask open questions and listen:

- "When you heard those examples, did anything resonate or spark something?"
- "Is there a topic, problem, or domain you keep coming back to in your own thinking?"
- "What's something you wish you thought about more clearly or consistently?"
- "Is there a question you've been sitting with that you haven't had time to properly chase?"
- "What would make a system like this actually useful for you — what would it do for your thinking?"

Listen for:
- A domain or topic they're drawn to
- A problem or friction they recognize
- A loop type that feels natural to how they already work
- Excitement about a specific capability (surfacing connections, generating prompts, building an answer over time)

Reflect back what you hear, but don't lock them in: "It sounds like you might be drawn to [what you heard]. You don't need to decide today — this is just the beginning."

## Specific Guidance

- **Don't push for a decision** — they have until Session 2 (ideation workflow) to shape this
- **No right answers** — any domain and any loop is valid if it's genuinely theirs
- **Capture loosely** — document what came up, not a polished concept

**Deliver:** Append to `docs/participant_profile.md`
- initial_use_case_thoughts (domain they mentioned, loops that resonated, problems they named, anything they're excited about)

**User Context:**
- Provides: Initial reactions to the use case, topics or problems that resonate
- Receives: The use case framing clearly introduced, their early thinking captured

**Confirm before continuing:** "Does this use case feel like something you could make genuinely yours — even if you're not sure yet exactly what it will be?"

---

### Step 5: Complete orientation by creating personalized Claude instructions and welcome message
**Goal:** Complete orientation by creating personalized Claude instructions and welcome message



## Personalize Claude Instructions

Using the information from their participant_profile.md, customize the Claude instructions to include:

1. **Technical Context Adaptation:**
   - Reference their current technical level
   - Mention their current tech stack and how it relates to bootcamp tools
   - Highlight their desired tech stack as learning objectives
   - Adjust technical explanations to match their expertise level

2. **Goal-Specific Guidance:**
   - Reference their specific bootcamp goals and success criteria
   - Customize examples to align with their project domain/interests
   - Include their time commitment and check-in rhythm

3. **Project-Focused Instructions:**
   - If they have a defined project idea, reference it specifically
   - If exploring options, mention their shortlisted areas of interest
   - Connect their technical approach preference to relevant sections

4. **Motivation Reinforcement:**
   - Reference their personal motivation for joining
   - Connect instructions to their desired outcomes
   - Use their language and terminology where possible

**Save the personalized CLAUDE.md file** to the workspace directory.

## Completion Message

Display an encouraging completion message confirming:
- Profile created with their background and goals
- Personalized Claude instructions ready
- Workspace setup complete and ready for next steps

**Deliver:** Save to `CLAUDE.md`

**User Context:**
- Provides: Confirmation that all setup steps are complete
- Receives: Welcome message and guidance for next steps

**Confirm before continuing:** "Are you ready to start using the bootcamp workflows?"

---

## Workflow Complete

All steps are complete. Update `docs/session_log.md` with your reflection and commit your changes.

---

## Output Artifacts

| File | Location | Description |
|------|----------|-------------|
| `participant_profile.md` | `docs/` | Full participant profile with background, goals, project idea |
| `CLAUDE.md` | `/` | Personalized Claude instructions |
