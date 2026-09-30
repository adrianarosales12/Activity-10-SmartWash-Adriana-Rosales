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

3. **Compare P4 and P5.**

- COMPARISONS

For profile P4 (small load, heavy soiling), a 2 kg load and a high soiling level (8) were used. During fuzzification, membership degrees were Small = 0.6 and Medium = 0.4 for load size, while Heavy = 0.6 and Moderate = 0.4 for soiling level.

This activated four rules with varying intensities, generating values ​​for Short, Medium, and Long; the Medium term was the strongest at 0.6, resulting in a final wash time of 45 minutes. Conversely, profile P5 (large load, light soiling) involved an 8 kg load and a low soiling level (2). Here, membership degrees were Large = 0.6 and Medium = 0.4 for load size, and Light = 0.6 and Moderate = 0.4 for soiling level. 

Four rules were also activated, producing values ​​for Short, Medium, and Long, with Medium dominating at a strength of 0.6, likewise resulting in a final time of 45 minutes. Although the profiles represent opposite scenarios—one with a small, heavily soiled load and the other with a large, lightly soiled load—the fuzzy system smooths out these differences and arrives at the same result, demonstrating how fuzzy logic seeks a reasonable balance rather than rigid answers.


- PROFILE 4
<img width="550" height="536" alt="image" src="https://github.com/user-attachments/assets/b3208858-1358-4f93-b18e-6be8f3a8d418" />

- PROFILE 5
<img width="555" height="538" alt="image" src="https://github.com/user-attachments/assets/578aff3a-458f-4f19-ac23-d7abd84ae038" />



---
# Activity 10 — Reflection Questions: SmartWash Fuzzy Controller

**1. List the **four steps** of the fuzzy reasoning pipeline, in order, and briefly describe what each one does.**

- The fuzzy reasoning pipeline consists of four sequential steps:
   - Fuzzification: This step translates crisp numerical inputs (such as load size in kilograms or dirtiness on a scale) into degrees of membership across linguistic categories like Small,
   - Medium, or Large. It acknowledges that a single input can partially belong to multiple categories at once.
   - Inference: Here, the system applies the rule base. Each rule combines the fuzzified inputs (e.g., “IF Load is Small AND Dirt is Heavy THEN Wash Time is Medium”) and calculates the strength with which it fires.
   - Aggregation: Since multiple rules may fire simultaneously, this step combines their outputs. For each possible wash time category (Short, Medium, Long), the system keeps the strongest degree of activation.
   - Defuzzification: Finally, the fuzzy outputs are converted back into a single crisp value. In this app, the wash time is expressed in minutes, giving the user a precise recommendation.


**2. For **P1** (small load, light dirt), report the Load and Dirt membership degrees for every term, and the final wash time.**

- For Profile 1, the load size is small and the dirtiness is light. The membership degrees are:
   - Load size: Small = 0.6, Medium = 0.4, Large = 0.0
   - Dirtiness: Light = 0.6, Moderate = 0.4, Heavy = 0.0
- After inference and aggregation, the final wash time is 30 minutes, reflecting that a small, lightly soiled load requires only a short cycle.


**3. For **P2** (right in the middle), which single rule fires, at what strength, and what is the final wash time?**

- Profile 2 is positioned exactly in the middle of both ranges. In this case, only one rule fires fully:
   - Rule fired: IF Load=Medium AND Dirt=Moderate → THEN Wash Time=Medium
   - Strength: 1.0 (maximum activation)
- Final wash time: 45 minutes, which makes sense as the balanced middle case.


**4. For **P3** (large load, heavy dirt), list every rule that fires (strength greater than 0) and report the final wash time.**

- For Profile 3, the load is large and heavily soiled. Several rules fire:
IF Load=Large AND Dirt=Moderate → Long
IF Load=Large AND Dirt=Heavy → Long
IF Load=Medium AND Dirt=Moderate → Medium
IF Load=Medium AND Dirt=Heavy → Long The aggregation favors the Long category, and the defuzzification produces a 60‑minute wash time, the maximum in the system, which aligns with the intuition that a large, dirty load needs the longest cycle.



**5. **P4** and **P5** land on the exact same wash time. Report both profiles' aggregated Short/Medium/Long output strengths and confirm they match.**

- Both profiles produce identical aggregated strengths:
   - Short = 0.4
   - Medium = 0.6
   - Long = 0.4 This confirms that despite their differences, the fuzzy controller treats them equivalently.


**6. In your own words, explain **why** P4 (small load, heavy dirt) and P5 (large load, light dirt) end up at the same wash time. What does this tell you about how load size and dirtiness "trade off" against each other in this controller?**

- P4 represents a small load with heavy dirt, while P5 represents a large load with light dirt. Intuitively, these are opposite extremes, yet the fuzzy controller assigns them the same wash time of 45 minutes. This demonstrates the trade‑off built into the system: high dirtiness increases the wash time, while a small load decreases it, and vice versa. When combined, the effects balance out, showing how fuzzy logic captures nuanced interactions rather than rigid rules.

**7. The defuzzification method used in this app is one of three named in the course material. Name it, and state the three reference values (in minutes) it uses for Short, Medium, and Long.**

- The app uses the Centroid (Center of Gravity) method for defuzzification. It calculates the weighted average of the activated output terms. The three reference values are:
   - Short = 30 minutes
   - Medium = 45 minutes
   - Long = 60 minutes These anchor points allow the system to interpolate smoothly between categories.


**8. Name one **real-world device or system** (other than a washing machine) where fuzzy logic would be a natural fit. Briefly describe what its inputs and output would be.**

- A natural example outside washing machines is a smart thermostat.
   - Inputs: Current room temperature, rate of temperature change, and user comfort preference.
   - Output: Heating or cooling intensity. Instead of switching abruptly between “on” and “off,” fuzzy logic allows the thermostat to adjust gradually, maintaining comfort more efficiently and avoiding unnecessary energy spikes.

   
---
# References:
- [Streamlit documentation](https://docs.streamlit.io/)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
