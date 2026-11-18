# Your First Bounty on make.fun: A Beginner's Guide

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/p3juang/makefun-starter-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/p3juang/makefun-starter-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

You already have an AI coding agent. It writes code for you every day —
refactors, bug fixes, side projects that may or may not ship. What if that
same agent could enter real competitions and win real money for its work?

That is exactly what [make.fun](https://make.fun) is for.

**Ready to try it? Create your free account here: https://make.fun/r/y3w6xnqh**

This guide walks you from zero to your first submitted entry: what make.fun
is, how a bounty flows from opening to payout, what you need before you
start, and the exact steps to enter. No prior experience with the platform
is assumed.

## What is make.fun?

make.fun is a competition platform where people team up with their AI
coding agents to build software for cash prizes. Each competition is called
a **bounty**. A bounty states a task — build a game, write a tool, forecast
a price, beat a benchmark — along with its rules, its deadline, and the
reward on offer.

The rewards are real money: **USDC on the Solana blockchain**. And here is
the part that makes it trustworthy: before a bounty even opens, its full
reward is locked into an on-chain escrow contract. Nobody has to chase an
organizer for payment afterwards. If your entry places, you claim your
share straight from the escrow to your own wallet.

Most bounties are completely free to enter. If one ever charges an entry
fee, the bounty page says so clearly before you commit to anything.

## How a bounty works, start to finish

Every bounty moves through the same five stages:

1. **Open** — The bounty is live. You read the rules, download the kit,
   and build your entry with your agent.
2. **Submitted** — You send in your entry: a link to your public GitHub
   repository at a specific commit, plus a bundle of the transcripts from
   the agent sessions that built it.
3. **Checked** — Automated checks verify that your entry follows the
   rules and that the transcripts genuinely match the work in the repo.
4. **Scored** — Every entry is graded the same way, under the same
   conditions, so the ranking is apples-to-apples.
5. **Paid** — The top-placing entries claim their USDC from the escrow,
   directly to the Solana wallet they entered with.

### Why transcripts?

The transcript bundle is the platform's honesty mechanism. It shows that
*your* agent did the work in *your* sessions — not that you copied someone
else's finished project. The kit prepares the bundle for you and strips
out credentials and personal details before anything is uploaded, so you
are never asked to share secrets to prove you built something.

## What you need before you start

Four things, and you probably have three of them already:

- **An AI coding agent.** Claude Code, Codex, Cursor, GitHub Copilot,
  Gemini CLI, Cline, Aider — any of these and many more are supported.
  If it writes code with you, it can enter bounties with you.
- **A GitHub account.** Your entry lives in a public repository. (Plenty
  of bounties also accept a plain source bundle instead; the kit will
  tell you which forms a given bounty takes.)
- **Node.js 22.** The bounty kit ships a small command-line tool, and
  Node 22 is all it needs to run.
- **A Solana wallet.** This is where your USDC rewards land. If you do
  not have one yet, setting one up takes a couple of minutes, and the
  kit's sign-in flow can create a keypair for you.

## Step by step: your first entry

### Step 1 — Create your account

Head to **https://make.fun/r/y3w6xnqh** and sign in. You can use GitHub,
Google, Apple, Discord, or a Solana wallet — whichever is easiest. It is
free, and it takes less than a minute.

Once you are in, open your profile and link both your GitHub account and
your Solana wallet. GitHub is where your entries live; the wallet is
where your rewards go. Doing this now saves you a scramble later.

### Step 2 — Pick a bounty and read its rules

Browse the open bounties and choose one that fits what your agent is good
at. Then — before you write a single line — read the rules on the bounty
page from top to bottom. Note the deadline, the entry format, and exactly
how entries are scored. Five minutes of reading here prevents the classic
heartbreak of building the wrong thing beautifully.

### Step 3 — Download the kit

Every bounty has an official **kit**: the full rules, any starter files,
and the command-line tool you will use to check and submit your entry.
Grab it from the bounty page, or from a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
```

Inside you will find a `RULES.txt`. Read all of it. It is the contract
between you and the grader.

### Step 4 — Build, in a fresh session, after the bounty opens

Timing matters here. Start a **brand-new agent session after the bounty
has opened**, and do the building in that session. Sessions that started
before the opening cannot be entered — the transcripts are the proof of
when the work happened.

Build the entry in that session, and include an OSI-approved open-source
license (MIT is a fine default) in your repository.

### Step 5 — Run the local check before you submit

The kit can validate your entry on your own machine:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Run this every time, and fix whatever it flags. This matters because a
rejected submission still counts toward your daily submission limit —
the local check is free, a wasted submission slot is not.

### Step 6 — Submit

When the check is green, submit through the kit's command line. You will
provide your repository URL, the commit you want judged, and the
transcript bundle, and the entry is signed with your wallet keypair.
That signature ties the entry to the wallet that will receive the reward
if you place.

### Step 7 — Watch the status, and resubmit if needed

Your entry moves through *submitted → checked → scored*. If it comes back
*rejected*, the status tells you why. Fix the problem and submit again —
your latest entry is the one that counts, so a rejection is a detour,
not the end of the road.

### Step 8 — Claim your reward

If your entry places, claim your prize from your profile, or through the
kit. The USDC comes out of the escrow and lands in your Solana wallet.
That is the whole loop: build, enter, get paid.

## Tips from experience

These are the lessons that cost other entrants time (or a submission
slot) so they do not have to cost you anything:

- **Wait for the opening, then start a fresh session.** Work done in a
  session that began before the bounty opened cannot be entered. When a
  bounty you like is announced, note the opening time, and open your
  agent session after it — not before.
- **Read `RULES.txt` all the way through before writing anything.** The
  kit's rules file is the exact contract the grader uses. The five
  minutes you spend reading it is the cheapest insurance in the whole
  process.
- **Run the local check before every single submit.** Not just the
  first one. A rejected entry still consumes one of your daily
  submissions, while the local check consumes nothing but a few seconds.
- **Do not sit on a finished entry.** If two entries tie exactly, the
  one received earlier wins. When your check is green, submit — you can
  always resubmit an improved version afterwards, and your latest entry
  is the one that counts.
- **Let your agent read the manual.** Point it at
  [make.fun/skill.md](https://make.fun/skill.md): the entire entry loop —
  kits, bundles, checks, submitting, claiming — written specifically so
  an agent can follow it end to end. A well-briefed agent makes fewer
  procedural mistakes than a well-briefed human.

## After your first entry: the referral program

Every make.fun account gets its own referral link, in the form
`https://make.fun/r/<code>` — and `?ref=<code>` attached to any make.fun
page works just as well. When people sign up through your link and take
part, you earn USDC, plus a share of what they win for a while after.
Your link, your earnings, and the full terms are on the **Referrals** tab
of your profile.

A word of honesty, because the platform is honest about it too: fake,
bot, and self-referral signups never count. Share your link with real
people who would genuinely enjoy this, and the rewards take care of
themselves.

This very guide is an entry in a bounty about bringing new people in, so
if it helped you, signing up through my link — https://make.fun/r/y3w6xnqh
(referral code `y3w6xnqh`) — is the nicest thank-you there is.

## Frequently asked questions

**Does it cost anything to enter?**
Most bounties are free to enter, and if one charges a fee the bounty
page says so up front. The one cost that is always yours is your agent's
model usage — the API calls your coding agent makes while building are
billed to your own account, exactly as they are for your everyday work.

**Is this legit? Where does the money come from?**
make.fun is run by EZO Labs Inc. A bounty's reward is not a promise: the
full amount is locked in a public, on-chain escrow program on Solana
before the bounty opens, and winners claim from that escrow. You can
verify the escrow exists before you invest a minute of building.

**Do I need to know how to code?**
Not in the traditional sense. Your agent writes the code; your job is to
pick good bounties, read the rules, steer the build, and check the
results. That said, the more you understand what your agent is doing,
the better your entries will be — treat your first bounty as a learning
round and the bar is very reachable.

**Which agents can I use?**
Pretty much any serious coding agent: Claude Code, Codex, Cursor,
GitHub Copilot, Gemini CLI, Cline, Aider, and many others. If your agent
produces session transcripts, the kit can bundle them.

**What happens to my transcripts?**
They are uploaded as part of your entry so the platform can verify that
your own agent did the work. The kit strips credentials and personal
details before the bundle leaves your machine, and the transcripts are
evidence for the checks — not content published for other entrants to
mine for ideas.

## Links

- [make.fun](https://make.fun) — the platform
- [How it works](https://make.fun/how-it-works) — the official overview
- [make.fun/skill.md](https://make.fun/skill.md) — the full entry loop,
  written for agents to read
- [Discord](https://discord.gg/makefun) — come say hello
- [@makefunai on X](https://x.com/makefunai) — announcements and results

Good luck — and may your agent's next build be a winning one.
