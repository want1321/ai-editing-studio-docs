# AI Editing Studio: documentation

**AI Editing Studio** is a Claude Code skill by [Artem Grigorets](https://grigorets.com/about) that turns raw talking-head phone clips into a finished vertical Reel for Instagram Reels, TikTok or YouTube Shorts. Put your clips in a folder, type `/studio-edit` in Claude Code, and Claude picks your best take of every line, cuts the pauses, cuts you out of the background, and adds captions, motion graphics and sound. You never open editing software: you watch the result, say what to change in plain words, and it re-renders in about two minutes.

This repository holds the documentation. The skill itself is a free download from [grigorets.com/studio](https://grigorets.com/studio); it is not distributed from this repository.

- Website: https://grigorets.com/studio
- Full guide: https://grigorets.com/studio/guide
- Free vs Pro: https://grigorets.com/studio/pay

## What happens when you type `/studio-edit`

1. **Finds and transcribes your clips.** It makes contact sheets and transcribes every take with word-level timing, locally on your computer.
2. **Keeps your best takes.** Repeat a line as many times as you like; it rebuilds your script and keeps the cleanest take of each line, with no dead air between them.
3. **Cuts from your original files.** Punch-ins from 4K footage stay sharp and add variety.
4. **Cuts you out of the background.** Big words can sit behind your head.
5. **Applies a designed look.** Captions, motion graphics and subtle sound design in a consistent style.
6. **Builds animated inserts.** For example an app on screen behind you, built in parallel by sub-agents.
7. **Checks every cut.** Everything stays inside the Instagram safe zone, and you get a phone-ready copy to review.

## Requirements

- A Mac, a Windows 10/11 PC or a Linux computer. Apple Silicon Macs are fastest for the background cutout
- A Claude plan that includes Claude Code. Your AI subscription is separate from Studio
- ffmpeg, Node.js 22 or newer and Python 3.10 or newer. On first run the skill prints the exact install line for anything missing
- About 10 GB of free disk space. The first Reel downloads about 2 GB of speech and cutout models
- A raw vertical clip of you talking to the camera

## Install

1. Get Free Studio from the [Free vs Pro page](https://grigorets.com/studio/pay). The download also includes [Footage Sorter](https://github.com/want1321/footage-sorter).
2. Copy the `studio-edit` folder into your Claude skills folder:
   - Mac and Linux: `~/.claude/skills/studio-edit`
   - Windows: `C:\Users\<you>\.claude\skills\studio-edit`
3. Open Claude Code and type `/studio-edit`. The first run asks your name, Instagram handle and favorite look, then checks your tools and sets everything up, once.

## Use

```text
/studio-edit I just dropped 5 clips in my downloads
```

Then give notes in plain words, for example "the captions feel too small" or "cut the pause before the last line". Each round re-renders in about two minutes.

Filming tips: shoot vertical in 4K if your phone allows, keep the camera still for each setup, and repeat a line until it feels right.

## Free vs Pro

| | Free | Pro |
|---|---|---|
| Editing formats | Talking head ("Yapping") | 10 formats: before/after, white frame, monochrome animation, character, yapping, greenscreen, tier list, split-screen reaction, head breakout, motion |
| Motion effects | 5 | 50+ |
| Caption styles | 5 | 50+ |
| Your own music, PNGs and video | Yes | Yes |
| Price | Free | $79 one-time within 48 hours of your first visit to a Studio offer page, $97 after |

Pro is an instant download: the download link is emailed right after payment. Check the [Free vs Pro page](https://grigorets.com/studio/pay) for the current price. Pro purchases have a full refund within 14 days of purchase. There is no Studio subscription; the Claude plan that runs it is separate.

## Who it is for

- **A good fit:** creators, coaches and founders who film themselves talking to the camera and want finished Reels without learning an editor; people who already use Claude and want their Reels to look the same every time, in their own style.
- **Not a fit:** anyone who wants to edit only on a phone, or who needs a hosted web editor or a hand-made edit by a human editor.
- **Would rather not set it up?** There is a done-for-you setup: your style is built from 2–3 Reels you love, you approve 3 finished Reels, and your own AI editor is then set up on your computer or your assistant's. The guides by audience below link to it.

## How it differs from editing apps

Timeline editors such as CapCut, and text-based editors such as Descript, give you tools and you make the edit yourself. Caption apps add captions to a video you upload to their cloud. AI Editing Studio works the other way around: Claude makes the whole edit from your raw takes on your own computer, and you direct it in plain language. You keep the files, your style is saved for the next video, and there is no Studio subscription.

## MCP video server or a local skill

If you want the edit to happen inside an AI chat, there are two routes, and they differ in where the video is made.

**An MCP server** connects Claude to a cloud video service. Nothing installs on your computer, it works from claude.ai, and the render happens on their infrastructure with their credits, so your footage goes to their storage. [JSON2Video](https://json2video.com/docs/v2/help-for-ai-agents/mcp-server)'s remote server accepts "public URLs only, up to 50 MB per file", so phone clips get uploaded in their dashboard first. [Shotstack](https://shotstack.io/solutions/agentic-video-editing/) renders free and watermarked in its stage environment and spends credits for production renders. [Descript](https://www.descript.com/mcp) and [Kapwing](https://www.kapwing.com/mcp) keep the project in your own account there and charge no separate MCP fee — AI steps spend the credits already on your plan.

**A Claude Code skill** is instructions Claude follows with the tools it already has: your shell, ffmpeg, local models. The render is local and there are no per-video credits. The cost is a one-time terminal setup and one machine: Anthropic's documentation says a personal skill works in "all your projects on this machine, but not Cowork or cloud sessions" ([Claude Code skills](https://code.claude.com/docs/en/skills)). AI Editing Studio is this route.

Pick MCP if you will not open a terminal, or if you render the same template hundreds of times. Pick a skill if your footage should not leave your computer, or if the look has to repeat without paying per video. Full comparison with each official page quoted: [MCP video server or local skill?](https://grigorets.com/studio/guides/edit-reels-with-claude-mcp-or-skill)

## Instagram's own tools first

Before any paid editor, use what Instagram gives you. **First draft** "allows you to create an editable reel draft from clips in your gallery or from the Instagram camera" ([Instagram Help Centre](https://help.instagram.com/3493297487510549/)) — the blank timeline problem, solved free, inside the app you post from. The **Edits** app is "free to download and use" on iOS and Android ([edits.instagram.com](https://edits.instagram.com/)), and since November 2026 there is a Mac version for Apple silicon with a multi-track timeline, keyframes, colour wheels, custom LUT and font import and 4K export with no watermark ([Edits for desktop](https://edits.instagram.com/desktop/)).

Where they stop: both hand you something to finish. First draft gives a draft, Edits gives a timeline, and you choose the takes, the captions and the look every time. No best-take-across-clips feature appears on either page, the desktop app is macOS with Apple silicon only, and neither official page documents driving Edits from Claude, ChatGPT or an MCP client.

So if you post one Reel a month, Instagram's free tools win on effort alone. Studio earns its setup when the same finishing work repeats — three a week, every one needing the same captions, punch-ins and look — or when you are on Windows or Linux. Detail: [Instagram First draft and Edits vs AI Reel editors](https://grigorets.com/studio/guides/instagram-first-draft-vs-ai-reel-editors).

## Compared with one-click auto-edit tools

A whole class of tools turns one uploaded video into a finished short in a click, and they are good at it. [Captions](https://captions.ai/help/docs/project/ai-edit)' AI Edit adds captions, B-roll, music, motion graphics, transitions and custom colour branding, and "detects pauses such as filler sounds (for example, 'um' and 'hmm')" to remove them; it asks for a single person talking, three minutes or less, and footage "not already be edited". [Submagic](https://care.submagic.co/en/article/how-to-use-ai-auto-edit-in-submagic-gaxw7t/)'s AI Auto Edit sets "captions and the caption theme", "B-rolls", "transitions", "zooms and camera movements" and "overall pacing and structure". [Descript](https://www.descript.com/mcp) names Remove Filler Words and Remove Retakes.

The line runs through the input. Every one of those works on a video you upload, so the choosing has already happened: you picked the take. AI Editing Studio starts a step earlier — several raw clips of you saying the same lines more than once — transcribes them with word-level timing and keeps the cleanest take of each line across the clips. No best-take-across-clips selection appears in the documented feature lists above; Descript's Remove Retakes is the nearest named feature. If you film one clean take and want it dressed up, a one-click tool is less work. If you film six takes of every line, the choosing is the job.

## Guides

- [How to edit Instagram Reels automatically with Claude](https://grigorets.com/studio/guide)
- [Claude Code skills that edit video: seven options compared](https://grigorets.com/studio/guides/claude-code-video-editing-skills)
- [Best AI video editors for talking-head Reels (2026)](https://grigorets.com/studio/guides/ai-video-editor-talking-head-reels)
- [CapCut alternatives that edit Reels automatically (2026)](https://grigorets.com/studio/guides/capcut-alternative-automatic-reels)
- [A ChatGPT or Claude workflow to auto-edit talking-head videos](https://grigorets.com/studio/guides/ai-workflow-talking-head-videos)
- [How to turn raw phone footage into a finished Reel in your own style, without editing software](https://grigorets.com/studio/guides/turn-phone-footage-into-reels-without-editing)
- [Edit Reels with Claude: MCP video server or local skill?](https://grigorets.com/studio/guides/edit-reels-with-claude-mcp-or-skill)
- [Instagram First draft and Edits vs AI Reel editors](https://grigorets.com/studio/guides/instagram-first-draft-vs-ai-reel-editors)

### By audience

- [Reels for business coaches: post every week without editing them yourself](https://grigorets.com/studio/guides/reels-for-business-coaches)
- [Reels for real estate agents: get your talking-head Reels edited every week](https://grigorets.com/studio/guides/reels-for-real-estate-agents)
- [Reels for online course creators: turn lessons into teasers for your course](https://grigorets.com/studio/guides/reels-for-course-creators)
- [Reels for loan officers: a weekly editing workflow that fits compliance review](https://grigorets.com/studio/guides/reels-for-loan-officers)
- [Hire a Reels editor or set up your own AI editor: an honest decision guide](https://grigorets.com/studio/guides/reels-editor-or-ai-editor)

## FAQ

**Is AI Editing Studio free?** Yes. Free Studio is a free download, together with Footage Sorter. Studio Pro is a separate paid edition with more formats, motion effects and caption styles.

**Does it work with ChatGPT?** No. AI Editing Studio works with Claude only: it is a Claude Code skill, so you need a Claude plan that includes Claude Code.

**Is my footage uploaded to a cloud editor?** No. Editing runs on your own computer. Claude Code talks to Anthropic for the AI part as usual, and the website never receives your raw clips.

**Does it work on a phone?** No. You film on your phone and edit on a Mac, Windows or Linux computer.

**Is it open source?** No. Free Studio is a free download. Footage Sorter, which comes in the same download, is open source under MIT.

## Author and support

Made by [Artem Grigorets](https://grigorets.com/about) ([Instagram @rtgrigorets](https://www.instagram.com/rtgrigorets/)). Support: value@grigorets.com.

AI Editing Studio is a product by Elvo LLC, 30 N Gould St Ste R, Sheridan, WY 82801, USA. Claude is a trademark of Anthropic. AI Editing Studio is not affiliated with or endorsed by Anthropic or OpenAI. This repository contains documentation only.
