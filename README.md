# Activity 10: SmartWash — A Fuzzy Logic Laundry Controller
## Sessions 17
## Due date (mm/dd/yyyy): 10/04/2026
## Adriana Rosales González
## Delivery Format: [] Video URL | [X] Markdown file | [] Jupyter Notebook file

---

## The Story

Real washing machines don't ask "is this load big or small?" as a strict Yes/No question — a
4 kg load isn't cleanly "small" or "medium," it's a bit of both. **Fuzzy Logic**, first proposed
by Lotfi Zadeh in 1965, lets a controller reason with exactly that kind of real-world
ambiguity, and still land on one precise decision. It's the same idea behind smart washers,
dryers, thermostats, and camera autofocus systems.

In this activity, you'll explore **SmartWash**, a small fuzzy controller that reads a load's
**size** and **dirtiness** and decides how many minutes to wash for.

This activity is a single interactive app — no coding required. Everyone in the class uses the
**same fixed rule base and membership functions, tested on the same five profiles** (there is no
randomness anywhere in the app), so your results should match your classmates' exactly.

---

1. **Read the Fuzzy Controller tab.** Look at the membership function charts and note that a value near the middle of the range belongs to *two* terms at once.
<img width="307" height="332" alt="image" src="https://github.com/user-attachments/assets/e4afab6e-f5f7-4939-8107-1e04e4add7af" /> <img width="313" height="338" alt="image" src="https://github.com/user-attachments/assets/6a8ac446-5028-419f-9d36-3cb3504d8411" />

2. **Run all five profiles (P1 through P5) in the Test the Controller tab.** Take a screenshot of the full breakdown for each one.

- PROFILE 1
<img width="548" height="542" alt="image" src="https://github.com/user-attachments/assets/59df02fa-dd2e-4c34-8d01-fe63bd5e967b" />

- PROFILE 2
<img width="551" height="491" alt="image" src="https://github.com/user-attachments/assets/a38e0b1e-4330-4b72-b948-7d250441bb85" />

- PROFILE 3
<img width="550" height="542" alt="image" src="https://github.com/user-attachments/assets/b1a7d896-0ae8-4e08-97df-8b3809113c2c" />

- PROFILE 4
<img width="550" height="536" alt="image" src="https://github.com/user-attachments/assets/b3208858-1358-4f93-b18e-6be8f3a8d418" />

- PROFILE 5
<img width="555" height="538" alt="image" src="https://github.com/user-attachments/assets/578aff3a-458f-4f19-ac23-d7abd84ae038" />

3. **Compare P4 and P5.** Take a screenshot showing both of their final wash times side by side.

---
# Activity 10 — Reflection Questions: SmartWash Fuzzy Controller

**1. List the **four steps** of the fuzzy reasoning pipeline, in order, and briefly describe what each one does.**

**2. For **P1** (small load, light dirt), report the Load and Dirt membership degrees for every term, and the final wash time.**

**3. For **P2** (right in the middle), which single rule fires, at what strength, and what is the final wash time?**

**4. For **P3** (large load, heavy dirt), list every rule that fires (strength greater than 0) and report the final wash time.**

**5. **P4** and **P5** land on the exact same wash time. Report both profiles' aggregated Short/Medium/Long output strengths and confirm they match.**

**6. In your own words, explain **why** P4 (small load, heavy dirt) and P5 (large load, light dirt) end up at the same wash time. What does this tell you about how load size and dirtiness "trade off" against each other in this controller?**

**7. The defuzzification method used in this app is one of three named in the course material. Name it, and state the three reference values (in minutes) it uses for Short, Medium, and Long.**

**8. Name one **real-world device or system** (other than a washing machine) where fuzzy logic would be a natural fit. Briefly describe what its inputs and output would be.**

   
---
# References:
- [Streamlit documentation](https://docs.streamlit.io/)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
