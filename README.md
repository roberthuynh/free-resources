# Free AI tools for student builders

Free AI tools, credits and student plans for building your first app, with the catch where there is one. I collected them for classmates at HBS, and most of it works for any student.

**Never built anything?** Plan your idea in Claude or ChatGPT, build it in v0, and share the link. Stop there until you need more.

Everything here was checked on October 31, 2026. Offers change often, so check the link before you count on a number. This is a personal list, not an official HBS, Harvard or MIT resource, and none of them reviewed it. I'm not affiliated with any of these companies, and no link here is a referral link.

## Contents

- [What you need](#what-you-need)
- [Claim this first](#claim-this-first)
- [Words you'll see](#words-youll-see)
- [Build your first app, step by step](#build-your-first-app-step-by-step)
- [When to pay, and what to avoid](#when-to-pay-and-what-to-avoid)
- [Add these when you need them](#add-these-when-you-need-them)
- [If you're taking a class at MIT](#if-youre-taking-a-class-at-mit)

## What you need

- A school email, to claim student plans.
- A laptop. Steps 1 to 4 happen in your browser, with nothing to install.
- A free [GitHub](https://github.com/signup) account, once you reach step 5.
- A card, but only for the plans that say so.

## Claim this first

**[v0 for Students](https://v0.app/students):** a free year of Vercel's app builder. Harvard is on its list of schools. It covers steps 2 to 4.

Claim the other plans when a step calls for them.

## Words you'll see

- **API key:** a password-like code that lets your app use an AI model. Keep it secret.
- **Environment variable:** a setting where your app keeps secrets such as API keys, outside its code.
- **Vercel:** the company behind v0. It keeps your app online.
- **Repo:** a project folder stored on GitHub, with every past version saved.
- **Coding agent:** an AI that edits and runs the code in your project while you describe the change.
- **Terminal:** the window where you type commands. On a Mac, press Cmd+Space and type Terminal. You only need it from step 5.

## Build your first app, step by step

Go in order. Steps 1 to 4 all happen inside v0 and your chat assistant, and most class projects stop there. Where a step has choices, it names a default first, the safe choice if you're unsure.

### 1. Plan with a chat assistant

Spend about 30 minutes turning your idea into a one-page spec: who it's for, the three or four screens, and what each one does. Later, paste errors here and ask what they mean.

- **At HBS:** HBS says students have ChatGPT and Claude ["from day one"](https://www.hbs.edu/mba/ai). Follow Harvard's [generative AI guidelines](https://www.huit.harvard.edu/ai/guidelines) on what data you can enter, and check each course's own AI policy before you use these for graded work.
- **Anywhere else:** the free plans of Claude, ChatGPT or Gemini all work. US college students can also get a free year of [Google AI Pro](https://gemini.google/students/) by December 31, 2026. Catch: it needs a card and bills $19.99 a month after the year, so set a reminder to cancel.

### 2. Build a first version in v0

Paste your one-page spec into [v0](https://v0.app/students) as your first prompt. v0 makes a working web app you can click through, and you improve it by chatting. Plan on about an hour.

To share it, select **Publish** at the top of the chat. Then open the link in a private browser window to check that classmates can see it.

- **Other option: [Figma Make](https://help.figma.com/hc/en-us/articles/360041061214-Figma-for-Education):** pick it if your team already works in Figma. It comes with the free Figma Education plan, which includes 3,000 AI credits a month. Figma Education is for coursework, and Figma says startups don't qualify.

### 3. Add AI with an API key

Skip this step unless your app itself should answer with AI. v0 adds the AI feature for you once it has a key: paste the key under the project menu, then **Settings**, then **Environment Variables**, and ask v0 to use it.

- **Default: [Gemini API](https://ai.google.dev/gemini-api/docs/pricing):** free Flash models with no billing setup. Get a key in [Google AI Studio](https://aistudio.google.com/apikey). Catch: on the free tier, Google uses what you send to improve its products, and people may read it. Keep confidential and personal data out, including your users' data. If people in Europe, Switzerland or the UK will use your app, Google requires the paid tier.
- **Other free tiers:**
  - **[OpenRouter](https://openrouter.ai/docs/api_reference/limits):** one key for many models. Models whose ID ends in `:free` cost nothing, up to 50 requests a day, or 1,000 a day once you've bought $10 of credits. Catch: outside providers run the free models, and some may log or train on your prompts. You can turn those providers off in OpenRouter's privacy settings.
  - **[GroqCloud](https://console.groq.com/docs/rate-limits):** very fast open models on a free plan. Catch: the limits differ by model and change often.
  - **[Cloudflare Workers AI](https://developers.cloudflare.com/workers-ai/platform/pricing/), [Mistral](https://docs.mistral.ai/getting-started/quickstarts/studio/activate-and-generate-api-key) and [NVIDIA NIM](https://docs.api.nvidia.com/nim/docs/product):** more free tiers with their own limits.
- **[Claude](https://platform.claude.com/docs/en/about-claude/pricing) and [OpenAI](https://openai.com/api/pricing/) APIs:** pay as you go. Use them when the free models aren't good enough.

**Keep your key safe.** Treat it like a password, and give v0 or your coding agent this instruction: *"Keep my API key in an environment variable, call the model only from server code, and never give the variable a name that starts with NEXT_PUBLIC_."* Never paste a key into a chat, a document or a repo. If one leaks, delete it in the provider's dashboard and make a new one.

**Before you share the link with a whole class:** free tiers cap requests per minute and per day, and a whole room opening your app at once can hit the cap. Server code hides your key, but anyone with the link can still use your app's AI and spend your quota. Set a spending limit with the provider, and add sign-in if the app will stay up.

### 4. Save data and let people sign in

- **Default: [Supabase](https://supabase.com/pricing):** a free Postgres database (where your app stores its data), with sign-in, file storage and a ready-made API. In v0, ask it to add a Supabase database, and it connects one for you. Catch: free projects pause after a week with no activity, and you get 2 active projects.

**Lock down your data.** Your app's public Supabase key is visible to anyone who opens it. Without Row Level Security, anyone can read, change or delete every row. Give v0 or your coding agent this instruction: *"Turn on Row Level Security for every table, with policies that let each signed-in user see and change only their own rows."* A policy that allows everyone is the same as no policy. Never put Supabase's secret key (called `service_role` in older projects) in front-end code or in an AI agent's settings.

### 5. Move to a coding agent when v0 isn't enough

You need this step when v0 keeps getting a change wrong, your app needs a Python backend, or you want to work on the code on your own computer. A coding agent works on the code in your repo. You describe the change, and it edits the files and runs them.

First, connect your v0 project to GitHub, so the agent starts from your code. Then claim these:

- **[GitHub Student Developer Pack](https://education.github.com/pack):** GitHub Copilot, GitHub Pro, Codespaces and a Heroku credit. Many of its offers end when you graduate.
- **[Codex for Students](https://developers.openai.com/community/students):** $100 of credits for OpenAI's Codex coding agent, for verified students at US and Canadian universities who live there. You claim it with your ChatGPT account, and the credits expire 12 months after you get them.

Pick an agent:

- **Default: [Codex](https://developers.openai.com/community/students).** Codex for Students covers it. If a course gives you Claude Code or Codex, use that instead. Claude Code needs a paid Claude plan or API credits.
- **Other options:**
  - **[GitHub Copilot](https://education.github.com/pack):** free with the Student Pack. Use it in Codespaces, a coding setup that runs in your browser, and you install nothing. The student plan picks the model for you.
  - **[OpenCode](https://opencode.ai):** an open-source agent for the terminal. It comes with free models and needs no account. Keep it updated, and note that some of its free models may use your prompts for training.
  - **[Antigravity](https://antigravity.google/pricing):** Google's coding agent, free with basic weekly limits. Google AI Pro raises them.
  - **[Jules](https://jules.google/docs/usage-limits/):** Google's agent that works on your GitHub repo in the cloud. Free for 15 tasks a day, or 100 with Google AI Pro.

### 6. Put it online

Built in v0? Publish already put it online with Vercel.

- **Default: [Vercel](https://vercel.com/pricing):** free hosting for websites. Connect your repo, and every change you push goes live. Catch: the free plan is for non-commercial use.
- **[Render](https://render.com/pricing):** for a Python backend, the server code behind your app. Catch: a free service sleeps after 15 minutes with no traffic and takes about a minute to wake.
- **[Heroku](https://education.github.com/pack):** $13 a month of credit for 24 months through the Student Pack, enough for a small app that stays awake.

## When to pay, and what to avoid

- **Cancel card-based trials before they bill.** Google AI Pro bills $19.99 a month after its free year.
- **Free and student plans are for learning.** Vercel's free plan is non-commercial, and Figma Education excludes startups. Move to a paid plan once your project charges customers or becomes a company.
- **Keep company data and personal data out of free tiers, and put course cases and readings only into tools your course allows.** Several free tiers use what you send to train or improve their models.

## Add these when you need them

### Your app is an agent that searches or reads the web

- **[Tavily](https://www.tavily.com/pricing):** web search for agents, with 1,000 free credits a month. Students get 4 months of the Project plan by emailing support from a school address. Catch: Tavily can use your queries to train models unless you turn off "Allow Use of Query Data" in your account settings.
- **[Exa](https://exa.ai/pricing):** a search API with $10 of free credit every month and no card. Catch: Exa uses search queries to train its models, so keep confidential details out of them.
- **[Firecrawl](https://www.firecrawl.dev/pricing):** turns web pages into clean text for your agent, with 1,000 free credits a month. Scrape only public pages that you're allowed to use.
- **[Langfuse](https://langfuse.com/pricing):** shows what your agent did at each step. Students get $200 a month for non-commercial work.

### You need a GPU

You only need one to train models or run large ones yourself.

- **[Modal](https://modal.com/pricing):** $30 a month of free GPU and CPU time. Usage past that is billed, so watch long GPU jobs.
- **[Google Colab](https://research.google.com/colaboratory/faq.html):** free notebooks with GPUs when they're available.

### You want to run models on your own laptop

- **[Ollama](https://ollama.com):** runs open models on your computer for free, with no API limits. Catch: small local models are less capable than hosted ones, and an app on Vercel can't reach a model on your laptop. Keep Ollama updated, and leave its server reachable only from your own computer, which is the default.

### You're making a game

- **[Unity Student](https://unity.com/products/unity-student):** a free year of the Unity Pro editor.

## If you're taking a class at MIT

HBS students can cross-register for MIT classes in the second (EC) year. MIT then gives you a Kerberos account for your time in the class. Some MIT tools accept it, and they're meant for your MIT coursework.

- **[Parley](https://mitsloanedtech.mit.edu/tools/claude/):** MIT's chat with Claude and other AI models. MIT Sloan says it's open to all MIT students, "including cross-registered students". Follow MIT's rules on what data you can enter.
- **[Parley API](https://orgchart.mit.edu/letters/parley-api-now-available-mit-community):** a personal key that works with Claude Code, Codex CLI and OpenCode. MIT gives graduate students $30 a month of API credit, but doesn't say whether cross-registered students get a key. Use it for your MIT class, not your own app or startup.
- **[Engaging cluster](https://orcd-docs.mit.edu/faqs/):** MIT's shared computing cluster. A Kerberos account gets you a free, lowest-priority account with GPUs. Use it for MIT coursework or research, not for a startup.

[Sloan's Claude Enterprise accounts](https://mitsloanedtech.mit.edu/tools/claude/) are not open to cross-registered students. MIT doesn't publish when a cross-registered student's account ends, so copy your files out when your MIT class ends.

## Contributing

Know a free tool or student offer that belongs here, or see a number that has changed? [Open a suggestion](https://github.com/roberthuynh/free-resources/issues/new?template=suggest.yml), or read the [contribution guidelines](CONTRIBUTING.md) to send a pull request.
