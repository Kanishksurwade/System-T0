# Day 3: The Integration Trap & AI Hallucinations

## 1. The Goal

Today's objective was to work around API token limits by connecting the OmniRoute GitHub repository to the Google Antigravity IDE. The idea was to create a more flexible development workflow, giving us access to a broad range of models while continuing the UI-to-code phase of **System: T-0**.

## 2. The Struggle

The installation and configuration process turned into a frustrating troubleshooting loop. I spent hours trying one suggested fix after another, only to find that many of the instructions did not match the actual setup or solve the problem.

ChatGPT repeatedly suggested incorrect solutions with a level of confidence that made them sound reliable. I ended up testing what felt like a hundred different options, revisiting steps, and losing time to explanations that kept changing instead of acknowledging when earlier instructions were wrong.

The biggest lesson from this part of the day was that persistence is useful, but repeatedly following unverified troubleshooting advice is not a productive engineering process.

## 3. The False Victory

Eventually, I managed to connect the tools using an extension called **Kilocode**. After hours of trial and error, the integration finally appeared to be working.

It felt like the breakthrough we had been working toward. But getting a connection working is only one part of the problem: the tools also need to support the actual work we want them to do.

## 4. The Dealbreaker

After the setup was complete, I discovered a critical limitation: the 280+ models available through OmniRoute were text-only for our use case. They could work with text, but they could not read or process the UI reference images I had designed in Canva yesterday.

That made the setup unsuitable for the current UI-to-code phase. Our immediate task is to turn visual designs into working interfaces, so image understanding is a core requirement—not an optional extra.

In other words, the integration worked technically, but it did not meet the project's actual needs. The hours spent configuring it did not move the UI implementation forward.

## 5. Lessons Learned (Key Takeaways)

- **Verify troubleshooting advice.** Do not blindly trust ChatGPT—or any AI assistant—when diagnosing a complex setup. Check commands, settings, and explanations against reliable documentation before spending hours trying them.
- **Check capabilities before installation.** Research a tool's exact feature set, especially multimodal and image-input support, before committing time to configuration.
- **A successful connection is not the same as a useful workflow.** Evaluate integrations against the task they must support, not just whether they connect.
- **Set a time limit for troubleshooting.** When repeated attempts are not producing evidence of progress, step back, verify assumptions, and reconsider the approach.

## 6. Next Steps

We are abandoning the Google Antigravity/OmniRoute setup for the current UI-to-code workflow. Instead, we will return to proven UI-generation tools such as **v0.dev** and investigate other multimodal alternatives that can accept our Canva designs as visual references and help convert them into code.

The priority is now clear: choose a workflow that can understand the designs first, then help implement them. No more spending hours integrating tools before confirming they can handle the job.

---

**Day 3 status:** Integration tested, key limitation identified, and approach pivoted.