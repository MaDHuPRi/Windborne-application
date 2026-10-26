# Software Engineer, Machine Learning Systems — Written Answers

Madhu Priya Pulletikurthi

## 1. A problem you couldn’t leave alone

My news pipeline worked fine on my laptop and then wouldn’t fit on a real server. It runs DistilBART for summaries, RoBERTa for sentiment, and NMF for topics. The free-tier AWS instance I had didn’t have enough RAM to hold all of them. I could have dropped a model or paid for a bigger box, but I wanted the whole thing live, not just on my machine. So I set up swap memory so the models could share the space, then wrote a systemd service so it starts on its own and restarts if it dies. It now runs all three models on that small instance, with inference under 30ms. It loads slower than it would on better hardware, and I know that. I’d still rather have it running on a cheap box than half-working on a nice one.

## 2. An unfamiliar system that wasn’t behaving

In May I started contributing to Nanda Town, MIT’s multi-agent testbed. I’d never seen the code. I started by getting it running locally and testing an existing agent through it. Then I was given a task: report.py described a stage inaccurately. The “processed” stage was one example. I read through report.py and the code around it to see what each stage actually meant before I touched the wording. The report said the seller “applied the task exactly once”, but Town never sees inside the seller and only counts the seller’s own acknowledgements, so the sentence claimed more than the evidence showed. I changed the wording so it says only what’s true, and I added 3 test cases to check the meaning holds, because a wording fix can quietly slip back later. That was one of my 3 pull requests so far. The other work is on the terminal UI design.

## 3. AI tools helped, and where I stepped in

I built my Causal Portfolio Recommendation Engine with an AI coding assistant. It has a lot of pieces: synthetic data, ETL, two models, MLflow tracking, a FastAPI layer, a dashboard, and 14 tests. The assistant saved me a lot of typing. But I read the code and debugged it myself, because I had to be able to explain every part. The real thinking came at the results. The causal model was closer on the true effects (error 0.596 vs. 0.604). The baseline scored higher on policy value. No tool told me what to do with that. I decided to report both and explain what each number measures. I’d rather someone see a mixed result than a clean story I couldn’t defend.

## 4. Production experience

Some, but not a team on-call setup. At UMBC I built and maintained a Python/PostgreSQL backend for the housing system. It supported 2,000+ resident records across 3 semesters of use. I also kept 15+ dashboards going for reports people read regularly, and ran ETL jobs on a Hadoop cluster. My news pipeline is live on AWS EC2 under a systemd service. I put my clinic query tool on office machines with Docker and no cloud. At KPMG I worked with a Jenkins deployment pipeline. I haven’t run anything with an uptime promise, been on a pager rotation, or built recovery for when a cloud node goes down. That’s the part of this role I’d be learning, and I’d rather say it now.

## 5. Years of relevant experience

About 2.5 years combined. That’s the Data & Systems Analyst role at UMBC (Oct 2024 – May 2026), the AI/ML Analyst Intern role at KPMG India (Jan – Jul 2024), and the Graduate Assistant role at UMBC (Oct 2025 – May 2026). Some of those overlap, so the calendar time is shorter than the sum. I also started research at DREAM Lab in September and have been contributing to Nanda Town since May. Most of what’s relevant here is backend, pipeline, and deployment work, not research.
