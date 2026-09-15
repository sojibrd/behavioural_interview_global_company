# behavioural_interview_global_company

big tech মানের কোম্পানির behavioral round-এর প্রস্তুতি: ছয়টা STAR story, ফল সংখ্যায়, একটা অন্যকে শেখানো নিয়ে; তারপর signal-এর ম্যাপ, দুই দৈর্ঘ্য, big tech-এর জোর আর কঠিন প্রশ্ন। `switch_in_6_month_global_company`-এর story-র কাজ দিন ধরে এখানে সরানো (ব্যবহারকারীর সিদ্ধান্ত ২০২৬-০৯-১৫) — plan-এ থাকে শুধু ঘর আর লিংক, রোজের ইংরেজি আর mock interview plan-এই। সাথে `behavioural_interview`-এর ২৫টা ডক, এই সাইটেই।

এটা তিনটা স্বাধীন পথের একটা — [লোকাল](https://sojibrd.github.io/behavioural_interview_local_company/) আর [রিমোট](https://sojibrd.github.io/behavioural_interview_remote_company/) আলাদা সাইট, প্রতিটা শূন্য থেকে শুরু। তিন পথেই ছয়টা story; পথ বদলালে বদলায় জোর।

**লাইভ:** https://sojibrd.github.io/behavioural_interview_global_company/

## Functional Requirement

- **আজ (`/`):** প্রথমবার খুললে শুরুর তারিখ জিজ্ঞেস করে — plan-এর সাথে চালালে plan-এর দিন ০০৬-এর তারিখ। তারপর দেখায় ক্যালেন্ডারের আজকের দিন, এই ক্রমে: জমে থাকা ⚑ → আজকের ঝালাই → আজকের দিন।
- **Rail:** সব পাতায় বাঁয়ে rail, মোবাইলে drawer — ৪টা পাতার লিংক, plan-এর gauge আর ব্লক; শুধু খোলা ব্লকের দিন।
- **দিন (`/day/<nnn>/`) · ব্লক (`/block/<slug>/`):** দিনের কাজ আর দিন বা ব্লক শেষের হ্যাঁ/না। story-র কাজ নেই এমন দিন "বিরতি", কেন ফাঁকা তা লেখা।
- **সূত্রের chip:** কাজে `(ডক ০২.০২)` থাকলে এই সাইটের ঐ ডকের পাতা।
- **ডক (`/docs/`, `/doc/<nn-nn>/`):** ২৫টা ডক পাঁচ স্তরে, পুরো লেখা; কোনটা এই পথের কোন দিনের কোন কাজে আসে।
- **ঝালাই (`/review/`):** প্রতিটা 🔁 কাজ টিকের দিন থেকে ১/৩/৭/২১ দিন পরে ফেরে।
- **নিয়ম (`/rules/`):** `docs/00-rules.md` হুবহু।
- **🧠 chip:** `learning_to_learn`-এর নীতি — chip চাপলে এক লাইনে কারণ, সাথে ঐ সাইটের লিংক।

## Non-Functional Requirement

- **সত্যের উৎস `docs/`।** কোডে কোনো দিন বা কাজ হার্ডকোড নেই। কাজের `(ডক nn.nn)` `guide/`-এ না মিললে, বা দিনের নম্বর পরপর না হলে **build ভাঙে।**
- **`guide/` = `behavioural_interview/docs/` হুবহু,** তিন পথে এক।
- **story-র লেখা এই repo-তে নয়** — সাইটে নোটের ঘর নেই, ইচ্ছাকৃত।
- **ফাইলে তারিখ নেই।** তারিখ = শুরুর তারিখ + (দিন − ১)। "আজ" মানে ক্যালেন্ডারের তারিখ, plan পেছায় না।
- **Static export → GitHub Pages।** Backend নেই।
- **Progress শুধু `localStorage`-এ,** একমাত্র `app/hooks/useProgress.ts` দিয়ে।
- **`app/lib/plan.ts` আর `app/lib/guide.ts` server-only।**
- **Theme contract অলঙ্ঘনীয়, সাইট dark-only।** chassis `system_design_*_company` থেকে; 🧠-এর তালিকা switch plan থেকে।
- **তিন পথের কোড একই।** পার্থক্য শুধু `app/lib/site.ts`, `next.config.ts`-এর basePath, `package.json`-এর নাম আর `docs/`।
- **স্ট্যাক:** Next.js 16, React 19, TypeScript, Tailwind v4, react-markdown।

## ডক ইনডেক্স

| ফাইল | দিন | Gist |
|---|---|---|
| [docs/00-rules.md](docs/00-rules.md) | — | লক্ষ্য, সত্যের উৎস, চিহ্ন, "আজ", সপ্তাহের ছন্দ, STAR story-র বসা, ঝালাই, ডকের পাতা, যা করবেন না, দিন ১৪৫-এর পরে |
| [docs/01-six-stories.md](docs/01-six-stories.md) | ০০১–০২৫ | ছয়টা STAR story, একটা একটা করে, তারপর ছয়টাই এলোমেলো প্রশ্নে |
| [docs/02-signal-map.md](docs/02-signal-map.md) | ০২৬–০৫৫ | story → signal ম্যাপ, নতুন প্রশ্ন, follow-up |
| [docs/03-two-lengths.md](docs/03-two-lengths.md) | ০৫৬–০৮৫ · dip | interviewer-কে আপনার প্রশ্ন, দুই দৈর্ঘ্য |
| [docs/04-big-tech.md](docs/04-big-tech.md) | ০৮৬–১১৫ · dip | big tech-এর behavioral — story আর সংখ্যা |
| [docs/05-hard-questions.md](docs/05-hard-questions.md) | ১১৬–১৪৫ · dip | প্রভাবের story, আট প্রশ্ন, ছয় signal ৩০ সেকেন্ডে, দুটো কঠিন প্রশ্ন |
| [guide/](guide/) | — | `behavioural_interview`-এর ২৫টা ডক, পাঁচ স্তরে: শুরু · সিগন্যাল · স্টোরি · ডেলিভারি · প্রশ্ন ব্যাংক |

## প্রজেক্ট-নির্দিষ্ট নিয়ম

### তথ্য বদলানোর ক্রম

`brainstorming/ASSUMPTIONS.md` → `brainstorming/` (`behavioural-how-many-paths.md`) → `switch_in_6_month_global_company/docs/` → এই ফোল্ডার। সাইটের দিন = plan-এর দিন − ৫ — plan-এর story-র ঘর আর এই সাইটের দিন একসাথে বদলান।

### ব্লক ফাইলের ছাঁচ

- `# ব্লক ১ — নাম` — প্রথম H1। "— "-এর পরের অংশ rail-এ দেখায়।
- `*দিন ০০১–০২৫ · plan-এর দিন ০০৬–০৩০*` — H1-এর নিচের italic লাইন। শেষে `· dip` থাকলে হোমে সতর্কতা আসে।
- `> **ব্লক শেষে:** …` · `### দিন ০০৭ · শিরোনাম` · `- [ ] ২৫′ …` · `> **দিন শেষে:** …`
- দিনের নম্বর সব ব্লক মিলিয়ে পরপর থাকতে হবে, না থাকলে build ভাঙে। কাজ ছাড়া দিন (`### দিন ০০২ · বিরতি`) চলে।
- কাজে `(ডক ০২.০২)` বা `(ডক ০৪.০১ · ডক ০৪.০৪)` = `guide/`-এর স্তর.ডক।
- `⚑` = মাইলফলক, `🔁` = ঝালাই হবে, শেষে `🧠 (নাম · নাম)`। নতুন 🧠 নাম লিখলে সেটা `app/lib/principles.ts`-এ যোগ করুন, তিন repo-তেই।

### Progress key

| key | মান |
|---|---|
| `gbi:v1:start` | শুরুর তারিখ `"YYYY-MM-DD"` |
| `gbi:v1:task` | কাজ শেষের তারিখ। id = দিন + কাজের **লেখা** থেকে hash |
| `gbi:v1:check` | দিন শেষ (`d007`) ও ব্লক শেষ (`b1`)-এর হ্যাঁ/না |
| `gbi:v1:review` | 🔁 ঝালাইয়ের অবস্থা `{ base, step }` |

## চালানো

```bash
npm install
npm run dev      # http://localhost:3000
npm run build    # static export → out/
```

push করলে `.github/workflows/deploy.yml` সাইটটা GitHub Pages-এ তোলে।
