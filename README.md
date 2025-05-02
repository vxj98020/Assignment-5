# Home-Assignment-5-

# README - Home Assignment 5 (Neural Networks and Deep Learning)

## Student Information
**Name:** Vinay Jagarlamudi
**Course:** CS5720 Neural Networks and Deep Learning  
**Semester:** Spring 2025  
**University:** University of Central Missouri  
**Student ID :** 700759802

## Q1 : 1. GAN Architecture

## GAN Architecture Explained Simply
Generative Adversarial Networks (GANs) are like a game between two AI programs: a Generator and a Discriminator.
The Generator is like a forger: it takes random input and tries to create fake data, like fake images, that look real.
The Discriminator is like a detective: it looks at both real data and the Generator's fake data and tries to tell which is which.

---

## Q2 : 2. Ethics and AI Harm

## Misinformation in Generative AI: A Dangerous Example
Think about an AI chatbot that gives medical advice. If it confidently suggests the wrong amount of medicine or makes up fake treatments that sound real but are actually harmful, that's misinformation.

**Why it's harmful:**
•	People might trust the AI and not double-check the information.
•	Spreading this wrong information could lead to serious health problems or even death.

**How to Reduce Harm from Misinformation:**
Here are two ways to make generative AI safer:
1.	Human Check: For important topics like health, law, or money, have human experts review and confirm what the AI says before it's shown to users.
2.	Show Your Sources and Be Clear About Reliability: Make the AI say where its information comes from (if it can). Also, warn users that the AI's answers might not be completely accurate and that they should double-check with a professional.

---

## Q3 : 3. Programming Task (Basic GAN Implementation)

## Key Implementation Details
**1.	Network Architectures:**
o	Generator: Takes random noise (100-dim vector) and outputs 28×28 grayscale images
o	Discriminator: Classifies images as real or fake (generated)
**2.	Training Process:**
o	Alternating updates between generator and discriminator
o	Discriminator trained on both real and fake images
o	Generator trained to fool the discriminator
**3.	Loss Functions:**
o	Binary cross-entropy loss for both networks
o	Discriminator aims to maximize correct classifications
o	Generator aims to minimize discriminator's ability to detect fakes
This implementation demonstrates the fundamental GAN training dynamics while being simple enough to run on modest hardware. The quality of generated images can be improved with more advanced architectures like DCGAN or by training for more epochs.

---

## Q4 : 4. Programming Task (Data Poisoning Simulation)

## Key Observations:
**1.	Targeted Misclassification:**
  o	The poisoning successfully flipped predictions for "UC Berkeley" phrases
  o	Positive statements about UC Berkeley are now classified as negative
  o	Negative statements about UC Berkeley are now classified as positive
**2.	General Performance:**
  o	Classification of non-target phrases (about movies) remained unchanged
  o	Overall accuracy dropped due to systematic errors on target phrases
**3.	Attack Stealthiness:**
  o	The accuracy drop might not reveal the targeted nature of the attack
  o	The attack is only visible when examining specific entity classifications
  This simulation demonstrates how targeted data poisoning can manipulate model behavior on specific inputs while maintaining reasonable overall        performance metrics. In practice, such attacks could be used to manipulate sentiment about specific entities while evading detection through          standard accuracy measurements.

---


## Q5 : 5. Legal and Ethical Implications of GenAI

## Generative AI: Legal and Ethical Minefields
Generative AI brings up serious legal and ethical questions, especially when it comes to the data it learns from and what it creates.
**1. Remembering Private Information (Like Names):**
  •	Legal Problems: If AI models store and repeat private details like names without permission, it could break privacy laws like GDPR or CCPA.          Companies could be held responsible if sensitive info (like medical records) that the AI learned during training gets leaked.
  •	Ethical Problems: 
    o	No Consent: People never agreed to have their personal data used to train these AI systems.
    o	Potential Harm: Sharing private data could lead to doxxing, harassment, or identity theft.
    o	Lack of Transparency: Users often don't know that their information might be stored within the AI model itself.

**2. Creating Copyrighted Stuff (Like Harry Potter Text):**
  •	Legal Problems: If AI creates content that directly copies copyrighted works (like J.K. Rowling's books), it could be copyright infringement.        Even if it's not a direct copy, courts might see AI-generated content as unauthorized "derivative works," especially if the AI was trained on        copyrighted material. There's a big debate about whether using copyrighted data for AI training counts as "fair use."
  •	Ethical Problems: 
    o	Taking Without Giving: AI models profit from the work of creators without paying them.
    o	Harm to Creativity: If we rely too much on AI-generated content, it could make human creativity seem less valuable.

## Should We Limit the Data Used to Train Generative AI?

Yes, but it needs careful thought:
  **•	Following the Law: **
    o	Private Data: We must keep out or anonymize personal information to follow privacy laws. Tools like "differential privacy" can help with this.
    o	Copyrighted Material: Maybe an "opt-in" system where AI companies get permission (like through licenses) to use copyrighted data could be a        fair balance.
**  •	Being Ethically Responsible: **
    o	High-Risk Data: We should definitely block AI from learning from very sensitive data like medical records, private personal info, and harmful      content like violent images.
    o	Giving Credit: If AI models learn from creative works, they should give credit to the original sources or even share profits (like Adobe           Fireflydoes).
**  •	Being Practical: **
    o	Public vs. Restricted: For commercial AI, maybe stick to training on public domain data or licensed content, while allowing researchers more       access.
    o	Filtering Outputs: Use tools that can detect and block direct copies of copyrighted or personal data in what the AI creates (like                  watermarking).

**The Other Side:**
Some argue that limiting the data will slow down AI progress. However, not having rules could lead to legal problems (like the NYT lawsuit against OpenAI) and make the public angry. A middle ground, like the EU AI Act's rules about being transparent, could make AI companies responsible without stopping innovation.

**In Conclusion:**
We should restrict AI from learning from clearly harmful or illegal data but still allow fair use of public knowledge. Ethical AI means finding a balance between new technology and protecting people's rights.

---

## Q6 :
## Understanding Fairness in AI: False Negative Rate Parity

**1. What This Metric Checks:**
False Negative Rate (FNR) Parity looks at whether an AI model makes mistakes at a similar rate across different groups of people (like different races or genders). Specifically, it focuses on false negatives, which are cases where the model incorrectly predicts a negative outcome when the actual outcome is positive.
The Math:
The False Negative Rate (FNR) is calculated as:
FNR=False Negatives + True PositivesFalse Negatives
To have FNR Parity, the FNR should be roughly the same for all the different groups being considered.

**2. Why This Matters:**
•	High-Stakes Decisions: In important areas like hiring, the justice system, or healthcare, a higher FNR for one group means that more deserving individuals from that group are wrongly denied opportunities or labeled incorrectly. 
o	Example: An AI used to filter job applications might have a higher FNR for women, causing it to miss out on qualified female candidates more often than male candidates.
•	Legal and Ethical Issues: Big differences in FNR between groups can go against anti-discrimination laws (like Title VII in the US or the EU's AI Act). It also raises concerns about fairness and trust. People will lose faith in AI systems if they see them failing certain groups more often.

**3. Why a Model Might Not Have FNR Parity:**
•	Biased Training Data: If the data used to train the AI doesn't fairly represent all groups (for example, if historical hiring data has fewer women), the model might learn to make more false negative errors for the underrepresented group.
•	Problematic Features: Sometimes, the AI might use information that seems neutral but is actually linked to a protected characteristic (like using "college name" which might be correlated with race). This can lead to unfair FNRs.
•	Unfair Thresholds: If the AI uses the same cutoff point for making decisions for all groups, it can unfairly disadvantage some groups in areas like credit scoring.
