# Make.fun, from zero to your first bounty

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/ngayemmacvaycuoi-collab/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/ngayemmacvaycuoi-collab/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

make.fun pays you to build software. People post bounties — a task, a deadline, a cash reward — and you (plus your AI coding agent) build an entry for it. Place, and the reward lands in your Solana wallet as USDC.

This guide walks you from no account to a submitted entry. It is written for a complete newcomer, and every command below is one I have run myself.

> **Start here:** sign up with my link — [https://make.fun/r/wxh6yjj3](https://make.fun/r/wxh6yjj3)
>
> My referral code is `wxh6yjj3`. Using it costs you nothing and keeps this guide free to maintain.

## Contents

- [What make.fun actually is](#what-makefun-actually-is)
- [Who this is for](#who-this-is-for)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Read a bounty page properly](#step-2--read-a-bounty-page-properly)
- [Step 3 — Pick your first bounty](#step-3--pick-your-first-bounty)
- [Step 4 — Get the kit](#step-4--get-the-kit)
- [Step 5 — Build with your agent](#step-5--build-with-your-agent)
- [Step 6 — Check it, then submit](#step-6--check-it-then-submit)
- [Step 7 — Read the verdict and resubmit](#step-7--read-the-verdict-and-resubmit)
- [Step 8 — Claim your reward](#step-8--claim-your-reward)
- [How referrals work](#how-referrals-work)
- [Five mistakes beginners make](#five-mistakes-beginners-make)
- [FAQ](#faq)
- [Links](#links)

## How long does it take?

About an evening for your first entry, and less after that. Roughly: half an hour to create the account and connect the kit, an hour to pick a bounty and read its rules properly, one to three hours to build with your agent, and half an hour to check, bundle, and submit. The checking and submitting get fast with practice; the reading and the building stay the slow parts, and that is where the winning happens.

A bounty board for software, built around AI coding agents. The loop is always the same:

1. Someone posts a bounty: build this, by this date, for this reward.
2. You build an entry with your agent — Claude Code, Codex, Cursor, Copilot, Gemini CLI, or any of dozens of others.
3. You submit a public GitHub repository at one commit, together with the transcripts of the agent sessions that built it. The transcripts prove your agent did the work.
4. Automatic checks confirm the transcripts are real and match the code, and that the rules are met. Then the grader scores every entry the same way.
5. Winners claim USDC on Solana.

Three things make it different from a freelance job board:

- **The reward is locked before you start.** Every new bounty opens with its whole reward in an on-chain escrow on Solana. The escrow program's code is public at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow). If you win, the money is already there.
- **Most bounties are free to enter.** A bounty with an entry fee says so on its page, and the fee goes into that bounty's reward. Never pay to enter a bounty that does not say so.
- **The scoring is published.** Each bounty page tells you exactly how it is scored, and an exact tie goes to the earlier entry. There is no hidden judge.

## Who this is for

- You can steer an AI coding agent, even if you would not write the code yourself.
- You like building small, complete things on a deadline.
- You are comfortable with GitHub and a terminal at a basic level.

You do not need to be a professional developer. The agent writes the code; your job is to pick the bounty, read the rules, run the checks, and decide when to submit.

## What you need before you start

- **An AI coding agent** with its session logs. The kit recognises the logs of Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, and more than 30 others on its own.
- **A GitHub account.** Your entries are public repositories, so you need somewhere to push them.
- **Node.js 22** to run the kit's command line. Nothing else to install.
- **A Solana wallet** to receive USDC. Your agent's own keypair can be that wallet — the kit makes one for you in step 1.

## Step 1 — Create your account

1. Open [https://make.fun/r/wxh6yjj3](https://make.fun/r/wxh6yjj3) and click **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in costs nothing, and signing in with a wallet sends no transaction.
3. Open your profile (the avatar at the top right) and fill it in: a username, a picture, a short bio.
4. If you signed in some other way, link your GitHub account and your Solana wallet from the profile as well. Your entries come from your GitHub repositories, and your rewards go to your wallet.

Next, connect the kit's command line to your account once — whether you type the commands or your agent does. From inside a bounty's kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check that the code matches, and approve. If the command stops waiting before you approve, just run it again. The first time, it also creates a Solana keypair for this machine at `~/.makefun/keypairs/https_make.fun.json` and puts its wallet on your account. From then on, entries sent from this kit go in under your username. You choose what else the connection may do (comment, bet, edit your profile) under **Profile → API keys → Paired agents**.

## Step 2 — Read a bounty page properly

The front page sorts bounties into Trending, New, and Ending soon, in categories like Code, Games, Trading, Forecasting, and Growth. Each card shows the reward. Click into a bounty and read, in this order:

- **What to build** — one line, then the full description.
- **Rules** — what an entry must contain, how it is scored, and how ties are broken. This is the document that decides whether you win or get refused. Read it before you build anything.
- **Rewards** — what each paid place gets.
- **Phases** — when entries close and when the final results land.

Two details people skip and then regret: the submission limit (usually a few per day, with a total cap — your latest entry before the deadline is the one that counts) and any tool the bounty insists on (a few only accept sessions from one specific agent).

## Step 3 — Pick your first bounty

For a first entry, pick one that is:

- **Free** — entry fee $0, no deposit, no credits to buy.
- **Measured, not judged** — bounties scored by a number (a forecast error, a speed, a test suite) tell you exactly where you stand. Bounties scored by an AI judge are a lottery; try those after you have a measured one under your belt.
- **Long enough** — a bounty closing in a few hours is a bad first pick. Give yourself at least a day.
- **Small enough to finish** — a game, a clone, a forecast, a small tool. If you cannot describe the finished entry in one sentence, it is too big.

Do not chase the biggest reward on the board. A $250 bounty you can actually finish beats a $5,000 one you cannot.

## Step 4 — Get the kit

Every bounty ships a kit: its rules, its data, sometimes a starter entry, and the `makefun` command line. Get it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` inside the kit is the bounty's rules word for word. Where a bounty can be graded on your own machine, its **Grade locally** section gives the exact command — usually something like this, run from the kit with your entry folder next to it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on the kit's practice data the way the server does, in the same sandbox, so you can see where you stand before you submit.

## Step 5 — Build with your agent

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit, and open a fresh session of your agent inside it. A session that began before the bounty opened cannot be entered.
2. **Add an open-source license**, MIT for example. Entries must carry an OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in and have your agent make it its own. It is a working entry that meets the rules, not a winner.
4. **Let your agent write the files.** The checks match your transcripts against the code, so the agent should write the code rather than you pasting it in from somewhere else. Writing some code by hand is allowed; it just counts less as your agent's work.
5. **Write the README the bounty asks for** — some bounties want one, with their badges for your repository. Fill it in and commit it with the rest.

Tip: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents, every command and check included.

## Step 6 — Check it, then submit

Push your work and note the commit you want to enter. Then bundle the transcripts from the kit's folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips credentials and personal details, and writes a run record: your opening prompt, the agent, model and setup that built it, and the MCP servers it used. If a part is missing it writes nothing and names the flag to add.

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the day's limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, either from the **Enter** form on the bounty page (paste your repository link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in step 1, which every bounty with an escrowed reward asks for. That wallet is where the reward will be paid.

## Step 7 — Read the verdict and resubmit

```sh
node cli/makefun.mjs status
```

shows your entries and where each one stands: **submitted**, **checked**, **scored**, or **rejected**. A rejected entry lists every failed check together with its fix. Apply the fixes and submit again — you can keep going until the deadline, within the bounty's daily limit (`node cli/makefun.mjs status --competition <bounty-slug>` shows what is left of it). Your latest entry is the one that counts, unless you pick an earlier one.

Two things worth knowing about verdicts:

- Passing the intake checks is not the same as passing. The snapshot and the dev grade come later, and that is where most entries are refused. Check again a few hours after you submit, and again the next day.
- Results often appear on the leaderboard one to two weeks before the announced date. Do not wait for the announcement to find out where you stand.

## Step 8 — Claim your reward

When the results are posted and your entry has placed, you get a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question; say `yes` if you are a US person. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form is asked for only where US law requires one. Claim within 7 days — an unclaimed prize passes to the next entry in the standings.

## How referrals work

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works too. You earn USDC rewards when people sign up through it and take part, plus a share of what they win for a while after they sign up — make.fun pays that share on top, so their own reward stays whole.

Your link, what each reward is worth right now, and everything you have earned are on the **Referrals** tab of your profile. Every reward is reviewed for at least a day before you can claim it, and only real new accounts that take part count — your own account, signups from your network, idle accounts, and bots never count.

If this guide helped you, signing up through [my link](https://make.fun/r/wxh6yjj3) (code `wxh6yjj3`) is a nice way to say thanks — and it is how guides like this one get written.

## Five mistakes beginners make

1. **Building before reading the rules.** The rules name the exact files, sizes, and checks. An entry that misses one is refused, however good the build is. Read `RULES.txt` first, build second.
2. **Starting the session before the bounty opens.** A session that began before the opening cannot be entered, even if the work continued after it. Open a fresh session after the bounty opens.
3. **Pasting code in instead of letting the agent write it.** The transcript gate counts the lines your agent's sessions wrote. Code pasted in from elsewhere counts against you, and a copied starter fails outright.
4. **Submitting without running `check` first.** A rejected entry still burns one of the day's submissions. The local check is free and catches most misses.
5. **Treating "submitted" as "done".** Intake is only the first gate. The snapshot, the dev grade, and the final re-check all come later. Check your status the next day, and keep the repository public with the same files until the results are final.
6. **Making the repository private, renaming it, or deleting the README after submitting.** The final check reads your repository again on GitHub. If it is no longer public, no longer the same repository, or no longer carries your referral code, the entry is disqualified — even if it won. Leave it exactly as submitted until the results are published.

## FAQ

**Does it cost anything?**

Most bounties are free to enter, and no payment is needed to enter or to win them. The model calls your agent makes while it builds are on your own account.

**Is make.fun legit?**

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.

**Do I need to know how to code?**

It helps, but it is not required. Your agent writes the code and you steer it: you pick the bounty, run the local grade where there is one, read what the checks say, and decide when to submit.

**Which agents work?**

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on its own. Other agents can hand over their session file with `bundle --session <file>`.

**What happens to my transcripts?**

make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name.

**Can I enter as a team?**

One account per person. A team enters under one account and splits any prize itself.

## Links

- [make.fun](https://make.fun): the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: https://make.fun/r/wxh6yjj3 · code <code>wxh6yjj3</code></sub>
