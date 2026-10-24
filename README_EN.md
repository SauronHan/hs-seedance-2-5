# hs-seedance-2-5

> **English** | [中文](README.md)

**Doubao Seedance 2.5 Native Prompt Compiler & Cinematic Choreographer (Agent Skill)**

Engineered specifically for generating top-tier cinematic AI videos with Volcengine's **Doubao Seedance 2.5** video foundation model. It strictly enforces the **Golden Four-Stage Structure** (Asset Pointer Mapping + Macro Style Summary + Micro-Timeline Progression + Global Audio-Visual & Negative Deadlock), two-stage character feature decoupling (preventing frozen/stiff faces), independent high-res reference anchoring, dual-color trajectory guidance, 3D animatic skeleton driving, and audio-visual crosstalk prevention.

---

## 🌟 Key Features

- **Native Transformer Attention Choreography**: Designed around the spatial-temporal attention mechanisms of Seedance 2.5, eliminating prompt drift, attribute bleeding, and floating hallucinations.
- **Two-Stage Feature Decoupling (Anti-Zombie Face)**: Explicitly strips static studio lighting and stiff neutral poses from reference assets, reserving all dramatic lighting, micro-expressions, and stage blocking for dynamic assignment along the timeline.
- **Three-Tier Motion Control Hierarchy (Mutually Exclusive & Fallback)**:
  - **Level 1 (Pure Text Timeline)**: For natural dialogue, slow tracking, and subtle macro movements (75% of scenes).
  - **Level 2 (Dual-Color Hand-Drawn Trajectories)**: Red arrows lock subject attack/displacement vector; blue arrows lock camera tracking trajectory, backed by strict **Line-Erasing Prompts (Trajectory Deadlock)**.
  - **Level 3 (3D Animatic / Mocap Skeleton)**: For complex multi-level verticality, close-quarters combat, and precise physics collisions, driven by 3D animatic geometry.
- **Audio-Visual Sync & Anti-Crosstalk Protocol**: Enforces unambiguous separation between native Foley/dialogue and external score (`MODEL_AUDIO_MODE`), strictly anchoring lip-sync and suppressing mechanical noise.
- **Zero-Dependency & Self-Contained**: Pure natural language compilation engine. Runs out-of-the-box in any client supporting AI Agent Skills (Claude Desktop, Antigravity, Cursor, etc.).

---

## 🛠️ Prerequisites

This skill is a pure **AI Prompt Compilation & Cinematic Sequencing Engine**:
- **Zero Local Environment Setup**: No Python libraries, no GPUs, and no API keys required locally.
- **Plug-and-Play**: Runs inside any LLM-powered agent framework.
- **Universal Output**: Generates production-ready task cards and copy-paste prompts compatible with Volcengine Console, Jimeng Web, or third-party Seedance platforms.

---

## 🚀 Installation & Usage

### Installation
Clone or copy this directory into your AI Agent's skills directory:

```bash
git clone https://github.com/your-username/hs-seedance-2-5.git
```

### Prompting Examples
Instruct your Agent in plain language:
> *"Compile a Seedance 2.5 operation card for this scene: A rainy night alley chase where the protagonist halts at a corner, glancing back in fear. David Fincher cold noir style, 14-second continuous long take."*  
> *"Create a 12-second macro tracking shot for a perfume commercial with Foley sound (glass clinking and liquid splashing), ready for Seedance 2.5."*

---

## 📂 Output Format & Examples

The Skill compiles a structured **Markdown Operation Card** containing input assets, parameters, and ready-to-use prompts:

```markdown
### SH001 Operation Card (Seedance 2.5)

- **Target Model**: Doubao Seedance 2.5 (14s, 16:9, 1080p, 24fps)
- **Reference Assets**:
  - `@Image1`: `CHAR_ZHANG_LOOKDEV.png` (Character DNA, ignore studio flat lighting)
  - `@Image2`: `LOC_ALLEY_RAIN_NIGHT.png` (Atmosphere & space baseline)
- **Control Level**: Level 2 (Dual-color vector trajectory guidance)

#### 📋 Native Prompt:
@Image1 @Image2 A cinematic neo-noir thriller scene. David Fincher cold desaturated aesthetic, 8:1 chiaroscuro side lighting.
[0:00-0:04] Camera dollies forward following the protagonist running down the rain-slicked cobblestone alley. Red trajectory guides his sudden sprint.
[0:04-0:09] At the blind corner, he skids to a halt, pressing his back against the wet brick wall, breath ragged, chest heaving.
[0:09-0:14] Camera pans in close to his face as his eyes dart sideways in panic. Raindrops stream down his temples.
--sound: Heavy footsteps splashing in puddles, distant sirens, harsh panting, deep sub-bass drone.
--negative: hand-drawn red blue lines, arrows, sketch marks, static zombie face, plastic skin, daytime, extra limbs.
```

---

## 📄 License

Private / MIT (See repository license).
