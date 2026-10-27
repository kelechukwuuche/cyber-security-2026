# Literature Review: Autonomous Penetration Testing

### Selected article

- **Title:** Autonomous penetration testing using reinforcement learning: A review and perspectives
- **Authors:** Jingju Liu et al.
- **Journal:** Expert Systems with Applications
- **Publication:** Volume 300 (2026), article 130219; available online 10 November 2025.
- **Article type:** Review article.
- **JUFO rating:** 2
- **DOI:** https://doi.org/10.1016/j.eswa.2025.130219

### Reason for selection
I selected this article because it connects the course theme of penetration testing with my career as a Senior Software Quality Engineer. Autonomous security testing is relevant to my interest in test automation, identifying software weaknesses, and improving testing efficiency. The review also examines the reliability and limitations of AI-driven testing, which are important considerations when assessing tools for quality assurance.


## b) Review the review

- **What are the key areas being researched?** 
The review identifies two main categories: attack path planning (using reinforcement learning to choose attack paths in simulated networks) and autonomous pentesting frameworks (where victims are agents in a vulnerable system interacting with real tools). Research efforts aim at addressing learning efficiency, large action spaces, dynamic networks, and transferability of learned strategies to unseen environments.

- **What’s widely agreed upon?**
Since pentesting involves a sequence of decisions, taken sequentially with some feedback from the environment, the literature explored here highlights reinforcement learning as one with promise in this space. Ongoing challenges involve large action spaces, sparse rewards, and poor generalisation. Simulators provide cheap and controllable training opportunities, but such training doesn't guaranty success in the real world. Modern frameworks have been proven feasible only in "simple environments" and have not proven strong autonomy.

- **What are the open questions?**
How can agents deal unseen networks, vulnerabilities, and tools without having to be retrained from scratch? How to deal with partial observations and map decisions into executable commands with tractable computation? How can training balance realism, efficiency, and safe exploration? Combining reinforcement learning with large language models, continual learning, and attacker–defender learning are proposed directions whose practical benefits still require validation.


## References

- Liu, J., et al. (2026). Autonomous penetration testing using reinforcement learning: A review and perspectives. *Expert Systems with Applications, 300*, 130219. https://doi.org/10.1016/j.eswa.2025.130219
- Karvinen, T. (2025). Start Your Research with a Review Article. https://terokarvinen.com/review-article/




## c) Threat modeling quickrun

*Fictional scenario. Probabilities and financial impacts are illustrative annual estimates.*

- **Company:** NordicShop, a Finnish online retailer with 30 employees and €5 million in annual revenue.
- **Crown jewels:** Customer information, order database, payment credentials, website availability, and customer trust.
- **Bad guys (COI):** Financially motivated cybercriminals.
  - **Capability:** Phishing, credential theft, and exploitation of vulnerable web applications.
  - **Opportunity:** Internet-facing services and employees with access to production systems.
  - **Intent:** Steal customer data or disrupt operations to demand payment. NordicShop is attractive because downtime directly affects sales.

### Two example risks

| Risk | Annual likelihood | Financial impact | Expected annual loss |
|---|---:|---:|---:|
| An attacker steals an administrator’s credentials through phishing and deploys ransomware, stopping sales and order processing for three days. | 20% | €200,000 | 0.20 × €200,000 = **€40,000** |
| An attacker exploits an API authorization flaw to download customer records, causing investigation costs and lost business. | 10% | €150,000 | 0.10 × €150,000 = **€15,000** |

### Decision on the biggest risk

- Priority: Ransomware – €40,000 per year.

- Mitigation: Phishing-resistant MFA for admins, limit production access, offsite backup, quarterly test restoration

- Management cost estimate: €12,000/year.

- The risk acceptance assumes a 5% residual probability for control exposure of €80,000 and a €4,000 annual loss.

- Reasoning: Reduced expected annual loss (36,000 EUR) > cost of annual control (12,000 EUR).




