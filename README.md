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
| Price | Free | $49 one-time |

Check the [Free vs Pro page](https://grigorets.com/studio/pay) for the current Pro availability. Pro purchases have a full refund within 14 days.

## Who it is for

- **A good fit:** creators, coaches and founders who film themselves talking to the camera and want finished Reels without learning an editor; people who already use Claude and want their Reels to look the same every time, in their own style.
- **Not a fit:** anyone who wants to edit only on a phone, or who needs a hosted web editor or a hand-made edit by a human editor.

## How it differs from editing apps

Timeline editors such as CapCut, and text-based editors such as Descript, give you tools and you make the edit yourself. Caption apps add captions to a video you upload to their cloud. AI Editing Studio works the other way around: Claude makes the whole edit from your raw takes on your own computer, and you direct it in plain language. You keep the files, your style is saved for the next video, and there is no Studio subscription.

Comparison of Claude Code video editing skills: https://grigorets.com/studio/guides/claude-code-video-editing-skills

## FAQ

**Is AI Editing Studio free?** Yes. Free Studio is a free download, together with Footage Sorter. Studio Pro is a separate paid edition with more formats, motion effects and caption styles.

**Does it work with ChatGPT?** Free Studio installs as a Claude Code skill, so today you need a Claude plan that includes Claude Code. A ChatGPT edition is being tested.

**Is my footage uploaded to a cloud editor?** No. Editing runs on your own computer. Claude Code talks to Anthropic for the AI part as usual, and the website never receives your raw clips.

**Does it work on a phone?** No. You film on your phone and edit on a Mac, Windows or Linux computer.

**Is it open source?** No. Free Studio is a free download. Footage Sorter, which comes in the same download, is open source under MIT.

## Author and support

Made by [Artem Grigorets](https://grigorets.com/about) ([Instagram @rtgrigorets](https://www.instagram.com/rtgrigorets/)). Support: value@grigorets.com.

AI Editing Studio is a product by Elvo LLC, 30 N Gould St Ste R, Sheridan, WY 82801, USA. Claude is a trademark of Anthropic. AI Editing Studio is not affiliated with or endorsed by Anthropic or OpenAI. This repository contains documentation only.
