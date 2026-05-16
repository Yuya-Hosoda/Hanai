# U9 Extraction — Step 5
## HRI Measurement Instruments — Adopt Group Only

**Governance Layer: ACTIVE**
- Clinical safety ≠ perceived safety. Trust ≠ therapeutic alliance. Comfort ≠ clinical benefit.
- Naturalness ≠ clinical efficacy. Social presence ≠ evidence of care quality.
- Unsupported construct transfers marked `[MATERIAL GAP]`.
- All L3 = PENDING — no claim moves to manuscript until direct source verification is complete.
- Content source labeled: **Sn** = search result snippet; **Tk** = training knowledge (requires direct verification).

**Created:** 2026-05-16
**Input:** `docs/literature/U9_hri_trust_safety_comfort_measurement_candidates.md`
**Adopt group:** C01, C03, C04, C05, C06, C07 (6 papers)

---

## Extraction Entries

---

### U9-C01 — Godspeed Questionnaire Series

| Field | Content |
|-------|---------|
| **Candidate ID** | U9-C01 |
| **Bibliographic metadata** | Bartneck, C., Külic, D., Croft, E., & Zoghbi, S. *Measurement Instruments for the Anthropomorphism, Animacy, Likeability, Perceived Intelligence, and Perceived Safety of Robots.* International Journal of Social Robotics, 2009. DOI: 10.1007/s12369-008-0001-3. |
| **Measurement construct** | Five constructs: (1) Anthropomorphism, (2) Animacy, (3) Likeability, (4) Perceived Intelligence, (5) Perceived Safety |
| **Instrument name** | Godspeed Questionnaire Series (GQS) |
| **Items / dimensions measured** | Five semantic differential subscales. Each item presents two opposing adjective anchors rated on a 5-point scale. Approximate item counts pending L3 verification [Source: Tk]: Anthropomorphism ~5 items (e.g., fake–natural, machinelike–humanlike); Animacy ~6 items (e.g., dead–alive, mechanical–organic); Likeability ~5 items (e.g., dislike–like, unfriendly–friendly); Perceived Intelligence ~5 items (e.g., incompetent–competent, ignorant–knowledgeable); **Perceived Safety ~2 items** (on the spectrum of threat perception, e.g., violent–gentle, aggressive–calm — exact items L3 PENDING). Total: approximately 23 items. [Source: Tk — exact item wording and count require direct source verification.] |
| **Target population / context** | General HRI; no specific population restrictions stated. Developed for evaluating robots across interaction contexts. Widely applied to humanoid, zoomorphic, and utilitarian robots. [Source: Sn, Tk] |
| **Applies to** | ✓ General HRI · ✓ Social robot interaction · ✓ Embodied agent interaction · ⚠ Mental-health robot context (requires context-transfer pilot; MG-U9-02) |
| **What claim it can safely support** | (1) Perceived Safety (GQS subscale) measures users' subjective perception of the robot as non-threatening — applicable as an operationalization of the physical/threat dimension of "perceived security" in RQ3. (2) Likeability subscale measures subjective positive regard for the robot — usable as a supporting naturalness/comfort measure. (3) Animacy subscale measures perceived aliveness — usable as a supporting naturalness measure. All claims must be framed as user perception, not system safety. [L3 PENDING] |
| **What claim it cannot support** | (a) Clinical safety of the robot or system — the scale measures user perception, not objective physical or clinical risk. (b) Therapeutic alliance or therapeutic rapport — the scale has no items assessing clinical relationship quality. (c) Symptom reduction or clinical improvement — the scale has no clinical outcome items. (d) That high Perceived Safety scores mean the system meets clinical safety standards — these are independent. |
| **Evaluation design relevance for RQ3** | **Primary instrument for "perceived security"**: Administer the Perceived Safety subscale pre/post interaction in both voice-only and voice+gesture conditions. Compare subscale means across conditions to assess whether gesture integration affects perceived security. May additionally administer Likeability and Animacy for "perceived naturalness." Recommend short form administration to reduce response burden in a within-subjects design. |
| **Overclaim risks** | (1) GQS Perceived Safety ≠ psychological security: the scale was designed for physical threat perception from the robot; psychological security in a mental health disclosure context is a related but distinct construct (MG-U9-03). Must not cite GQS scores as evidence of psychological security without construct-validity argument. (2) GQS context transfer: the scale was validated across general HRI contexts; applying it to a mental health support context requires pilot validation (MG-U9-02). (3) High GQS Perceived Safety score ≠ clinical safety endorsement. |
| **L1** | ✓ |
| **L2** | ✓ (IJSR Springer DOI + full authors confirmed) |
| **L3** | PENDING — exact item wording and subscale item counts require direct source verification before any item-level claims are made in the manuscript |

---

### U9-C03 — Hancock et al. 2021 Evolving Trust Meta-Analysis

| Field | Content |
|-------|---------|
| **Candidate ID** | U9-C03 |
| **Bibliographic metadata** | Hancock, P.A., Kessler, T.T., Kaplan, A.D., Brill, J.C., & Szalma, J.L. *Evolving Trust in Robots: Specification Through Sequential and Comparative Meta-Analyses.* Human Factors, vol.63, no.7, pp.1196–1229, 2021. DOI: 10.1177/0018720820922080. |
| **Measurement construct** | Trust in human-robot interaction — theoretical framework and evidence synthesis |
| **Instrument name** | Not a primary measurement scale; meta-analytic review providing the theoretical model for trust operationalization. Identifies and synthesizes existing trust measures across 29+ empirical studies. |
| **Items / dimensions measured** | Three overarching factor categories for trust antecedents: (1) Human factors (user characteristics, experience, personality); (2) Robot factors (robot performance, attributes, appearance, behavior — found to have the greatest association with trust); (3) Environmental / contextual factors (task type, stakes, interaction duration). [Source: Sn, Tk] Note: C03 is a meta-analysis, not a measurement instrument; it does not specify a fixed item set. |
| **Target population / context** | Meta-analysis across multiple HRI empirical studies; covers general HRI, collaborative robotics, and social robot contexts. No specific mental-health robot studies confirmed within the meta-analysis scope at this stage (L3 PENDING). |
| **Applies to** | ✓ General HRI · ✓ Social robot interaction · ⚠ Embodied agent interaction (coverage pending L3 verification) · ⚠ Mental-health robot context (no confirmed coverage) |
| **What claim it can safely support** | (1) Theoretical framing: trust in robots is a multidimensional construct influenced by human, robot, and contextual factors — this framework is appropriate for situating the proposed RQ3 trust measurement in the HRI trust literature. (2) Robot performance and behavior are among the strongest factors associated with trust — supports the hypothesis that voice+gesture coordination (robot behavior) may affect trust. (3) Environmental/contextual factors moderate trust — justifies including condition (voice-only vs. voice+gesture) as a trust-moderating contextual variable. All claims are theoretical framing, not direct measurement endorsements. [L3 PENDING] |
| **What claim it cannot support** | (a) That trust in a mental health support robot constitutes therapeutic alliance — the meta-analysis covers HRI trust broadly, not clinical therapeutic relationships. (b) That higher trust scores indicate better mental health outcomes — no clinical outcome data in a meta-analysis of trust antecedents. (c) A specific item set or scale for the proposed study — C03 synthesizes trust measures but does not prescribe one for this context; specific instrument selection deferred to C05. |
| **Evaluation design relevance for RQ3** | **Framework role (not primary instrument)**: Use C03's three-category model to structure the Discussion of trust results in RQ3. Specifically: if gesture integration affects trust (RQ3 result), attribute the effect to "robot behavior" (robot factor category) per the C03 framework. Cite C03 as the theoretical basis for treating trust as a multidimensional construct rather than a single-item global measure. |
| **Overclaim risks** | (1) Do NOT cite C03 as a measurement scale — it is a meta-analysis, not an instrument. (2) Do NOT claim C03 establishes that trust improvement leads to therapeutic benefit — no such causal chain is in the meta-analysis. (3) Do NOT generalize trust factors from industrial/collaborative HRI contexts to mental health support without qualification. |
| **L1** | ✓ |
| **L2** | ✓ (SAGE DOI + full authors confirmed) |
| **L3** | PENDING — coverage of mental-health robot studies within the meta-analysis requires direct source verification |

---

### U9-C04 — Rubagotti et al. 2022 Perceived Safety Survey

| Field | Content |
|-------|---------|
| **Candidate ID** | U9-C04 |
| **Bibliographic metadata** | Rubagotti, M., Tusseyeva, I., Baltabayeva, S., et al. *Perceived Safety in Physical Human–Robot Interaction — A Survey.* Robotics and Autonomous Systems, vol.151, art.104047, 2022. DOI: 10.1016/j.robot.2022.104047. |
| **Measurement construct** | Perceived safety in physical human-robot interaction — survey of assessment factors and methods |
| **Instrument name** | Not a single scale; comprehensive survey of perceived safety assessment methods. Identifies six key factors and multiple assessment approaches (questionnaires, physiological measures, behavioral measures, direct input devices). |
| **Items / dimensions measured** | Six factors closely related to perceived safety (from search snippets, L3 PENDING for exact taxonomy): (1) Context of robot use, (2) Comfort, (3) Experience and familiarity with robots, (4) Trust, (5) Sense of control over the interaction, (6) Transparent and predictable robot actions. Assessment methods reviewed include: questionnaire-based measures, physiological measurement (galvanic skin response, heart rate), behavioral assessment, and direct input devices. [Source: Sn] |
| **Target population / context** | Physical HRI in six robot categories: industrial poly-articulated manipulators, indoor mobile robots, mobile manipulators, humanoid robots, drones, autonomous vehicles. Emphasis on physical proximity and physical safety perception. |
| **Applies to** | ✓ General HRI (physical proximity contexts) · ⚠ Social robot interaction (partially — some humanoid robot studies included) · ✗ Embodied agent interaction (no clear coverage confirmed) · ✗ Mental-health robot context (no confirmed coverage) |
| **What claim it can safely support** | (1) Six factors — particularly "sense of control" and "transparent and predictable actions" — are relevant perceived safety constructs for the proposed system's voice+gesture interaction, where predictability of gesture timing and transparency of system behavior are design features. (2) The survey supports the selection of questionnaire-based assessment as an appropriate perceived safety measurement method for the proposed RQ3 user study. (3) Factors of comfort and trust are co-occurring components of perceived safety — supporting the composite operationalization of "perceived security" that combines multiple subscales. All claims are about factor structure and measurement method selection. [L3 PENDING] |
| **What claim it cannot support** | (a) Physical safety claims — the survey reviews physical proximity safety; the proposed system's safety is about psychological and functional boundaries, not physical proximity risk. (b) Clinical safety assessment — perceived safety in HRI ≠ clinical risk management for mental health. (c) That good perceived safety scores on C04-derived items constitute evidence that the proposed system is clinically safe. |
| **Evaluation design relevance for RQ3** | **Item source for "perceived security" composite**: Extract items or item templates addressing "sense of control over the interaction" and "transparent/predictable robot actions" from C04-reviewed questionnaires, adapting them for the voice+gesture dialogue context. These items supplement the Godspeed Perceived Safety subscale (C01) to cover the psychological security dimension that Godspeed does not fully address. Specifically: transparency items address whether the user understands what the robot is doing and why — relevant to "perceived security" in the mental health support context. |
| **Overclaim risks** | (1) The survey focuses on PHYSICAL HRI safety perception — do NOT cite C04 as evidence for psychological security measurement without explicitly noting the construct extension. (2) Do NOT cite C04 as if it validates items for mental-health robot contexts — it does not. (3) C04 is a survey paper, not a validation study — it identifies factors but does not provide validated scale items; item adaptation requires expert review. |
| **L1** | ✓ |
| **L2** | ✓ (ScienceDirect DOI + lead authors confirmed; full co-author list TBC) |
| **L3** | PENDING — exact taxonomy structure and factor definitions require direct source verification; the six-factor structure is from search snippets only |

---

### U9-C05 — JMIR 2024 Systematic Review of HRI Measurement Instruments

| Field | Content |
|-------|---------|
| **Candidate ID** | U9-C05 |
| **Bibliographic metadata** | Authors unconfirmed (full list TBC). *Instruments for Measuring Psychological Dimensions in Human-Robot Interaction: Systematic Review of Psychometric Properties.* Journal of Medical Internet Research (JMIR), 2024. DOI: 10.2196/55597. PMC:PMC11187516. |
| **Measurement construct** | Meta-review covering psychological dimensions in HRI: attitudes, beliefs, opinions, feelings, and perceptions toward social and domestic robots |
| **Instrument name** | Systematic review covering 27 validated instruments across 34 studies — not itself a scale. Key instruments identified include (from search snippets): Godspeed series, Networked Minds Social Presence Inventory, Robot Attributes Scale, and others (exact list L3 PENDING). |
| **Items / dimensions measured** | Across 27 reviewed instruments: structural validity (assessed in 24/27 instruments, 89%) and internal consistency (assessed in 26/27, 96%) are the most evaluated psychometric properties. Measurement error and responsiveness were not evaluated for any instrument. Most instruments target adults and older adults (≥18 years). Instruments cover dimensions including: attitudes toward robots, trust, social presence, perceived usefulness, perceived safety, anxiety, acceptance. [Source: Sn] |
| **Target population / context** | Social and domestic robots; studies include elderly care, home robots, and general HRI contexts. Healthcare robot contexts have limited coverage — the review notes this as a specific gap. Target populations: adults (63% of instruments), older adults, limited coverage of children. |
| **Applies to** | ✓ General HRI · ✓ Social robot interaction · ✓ Embodied agent interaction (social/domestic robots) · ⚠ Mental-health robot context (explicitly flagged as a gap in the review itself) |
| **What claim it can safely support** | (1) Of the 27 instruments reviewed, those with established structural validity and internal consistency (meeting the 89%/96% criteria) can be cited as having adequate basic psychometric properties for use in the RQ3 user study — pending identification of the specific instrument via L3 verification. (2) The review confirms that no existing HRI instrument evaluates measurement error and responsiveness in clinical contexts — directly supports MG-U9-01 and the limitation statement that the proposed study uses instruments without clinical-context responsiveness data. (3) The review supports the selection of instruments targeting adults (≥18) as appropriate for the proposed study population. [L3 PENDING] |
| **What claim it cannot support** | (a) That any specific instrument from the 27 reviewed is validated for the mental-health robot context — the review itself notes limited healthcare coverage. (b) That measurement equivalence across robot types is established — the review covers multiple robot contexts and equivalence across them is not asserted. (c) Clinical validity of any instrument — structural validity and internal consistency do not constitute clinical validation. |
| **Evaluation design relevance for RQ3** | **Primary instrument selection guide**: Use C05 to identify which of the 27 reviewed instruments has the best psychometric properties (structural validity + internal consistency + appropriate target population) for measuring trust in the proposed RQ3 user study. Specifically: (a) Identify trust-measuring instruments within the 27; (b) Select the one with structural validity, internal consistency, and adult target population; (c) Verify the instrument's items via L3 before use. This step is essential for fulfilling the JMIR 2024 review's implicit guidance that instrument selection should be based on psychometric evidence, not convenience. |
| **Overclaim risks** | (1) Do NOT cite C05 as validating a specific instrument for the proposed context — the review surveys psychometric properties of existing instruments but does not validate them for a new context. (2) Do NOT imply that instruments included in this review are appropriate for clinical measurement — the review explicitly notes the absence of clinical-context psychometric data. (3) Authors unconfirmed — resolve before final citation. |
| **L1** | ✓ |
| **L2** | Partial (JMIR DOI + PMC confirmed; full authors TBC — MG-U9-05) |
| **L3** | PENDING — specific instrument recommendations require reading the full review to identify which of the 27 instruments best meets RQ3 requirements |

---

### U9-C06 — Heerink et al. 2010 Almere Model

| Field | Content |
|-------|---------|
| **Candidate ID** | U9-C06 |
| **Bibliographic metadata** | Heerink, M., Kröse, B., Evers, V., & Wielinga, B. *Assessing Acceptance of Assistive Social Agent Technology by Older Adults: The Almere Model.* International Journal of Social Robotics, 2010. DOI: 10.1007/s12369-010-0068-5. |
| **Measurement construct** | User acceptance of assistive social agent/robot technology — multi-construct model |
| **Instrument name** | Almere Model (questionnaire) — adaptation of the Unified Theory of Acceptance and Use of Technology (UTAUT) extended with social HRI variables |
| **Items / dimensions measured** | Eleven constructs measured via Likert-scale statements (7-point: strongly disagree to strongly agree) [Source: Tk — exact items require L3 verification]: (1) Social Influence, (2) Social Presence, (3) Perceived Usefulness, (4) Perceived Ease of Use, (5) Perceived Adaptivity, (6) Perceived Sociability, (7) **Trust** (belief that the agent acts in the user's interest), (8) **Anxiety** (negative affect toward using the robot), (9) Intention to Use, (10) Actual Use, (11) Experience (covariate). Model accounts for 59–79% of variance in usage intentions and 49–59% in actual use. [Source: Sn, Tk] |
| **Target population / context** | Elderly adults (≥65) in elderly care facilities and home settings; validated with the iCat robot (cartoon cat-like appearance, non-mobile, with facial expression capability). Three different social agents tested across controlled experiments and longitudinal studies. |
| **Applies to** | ✓ Social robot interaction · ✓ Embodied agent interaction · ⚠ General HRI (validated only in assistive/care context, not industrial) · ⚠ Mental-health robot context (analogous care-support context; population transfer requires pilot testing — MG-U9-02) |
| **What claim it can safely support** | (1) The Trust subscale ("belief that the agent tries to bring about interactions that are favorable for the user") provides a validated item set for measuring robot trust in an assistive social agent context — directly applicable to the proposed system's user-trust measurement. (2) The Anxiety subscale (inverted) provides items measuring comfort/freedom from negative affect during robot interaction — applicable to the "perceived comfort" component of RQ3's "perceived security" construct. (3) The Social Presence subscale supports measurement of naturalness/social presence perception. All claims treat these as user-perception measures. [L3 PENDING] |
| **What claim it cannot support** | (a) Clinical therapeutic trust or therapeutic alliance — the Trust construct in the Almere model is "perceived agent benevolence," not clinical therapeutic relationship quality. (b) Clinical anxiety reduction — Anxiety in the Almere model is a user-perception measure of discomfort with technology, not a clinical anxiety assessment instrument. (c) Generalization to non-elderly populations without pilot testing — the model was validated exclusively with elderly users. (d) Generalization to voice+gesture robots without construct-transfer validation — the iCat has a very different form factor from a full-duplex voice+gesture robot. |
| **Evaluation design relevance for RQ3** | **Trust and Anxiety subscales for "perceived security" composite**: (1) Use the Trust subscale items to measure the trust component of RQ3 (supplementary to the validated trust scale identified via C05). (2) Use the Anxiety subscale items (inverted to indicate comfort/security) as components of the "perceived security" composite operationalization — specifically for the psychological safety-in-disclosure dimension not covered by Godspeed Perceived Safety. (3) If user acceptance is a secondary RQ3 measure, administer the Almere short form (Perceived Usefulness + Trust + Social Presence + Anxiety + Intention to Use subscales). Note: requires pilot testing with the proposed population (MG-U9-02). |
| **Overclaim risks** | (1) Almere Anxiety subscale measures discomfort with the robot, NOT clinical anxiety — do NOT cite Almere Anxiety scores as clinical anxiety measures or as evidence of reduced anxiety disorder symptoms. (2) Almere Trust subscale measures perceived agent benevolence, NOT therapeutic alliance — do NOT describe it as measuring clinical therapeutic trust. (3) The model was validated with elderly users of a cartoon-cat robot — do NOT claim Almere is validated for the proposed system's specific context without pilot testing. |
| **L1** | ✓ |
| **L2** | ✓ (IJSR Springer DOI + full authors confirmed) |
| **L3** | PENDING — exact Trust and Anxiety item wording requires direct source verification before manuscript use; population-transfer validity for the proposed context requires pilot study |

---

### U9-C07 — Robot Social Presence Measurement Dimension Scale

| Field | Content |
|-------|---------|
| **Candidate ID** | U9-C07 |
| **Bibliographic metadata** | Authors unconfirmed (full list TBC — MG-U9-05). *Development and Validation of a Robot Social Presence Measurement Dimension Scale.* Scientific Reports (Nature Portfolio), 2023. DOI: 10.1038/s41598-023-28817-4. PMC:PMC9939412. |
| **Measurement construct** | Robot social presence — the user's perception of the robot as a social being during interaction |
| **Instrument name** | Robot Social Presence Measurement Dimension Scale (name TBC — exact instrument title requires L3 verification) |
| **Items / dimensions measured** | Five dimensions (from search snippets [Source: Sn]): (1) Presence (awareness of the robot as an entity in the interaction), (2) Attention distribution (perception of mutual attention), (3) Interactive expression and information understanding (perception of communicative exchange quality), (4) Perceived emotional interdependence (sense that emotions are shared/recognized), (5) Interaction behaviour perception (evaluation of the robot's interactive behavior). Total: 17 items across five dimensions. Scale validation methods and sample characteristics: L3 PENDING. |
| **Target population / context** | Social robots in general — scale developed for measuring social presence specifically with robot interaction partners (as distinct from virtual agent or avatar social presence). Context of validation study: TBC via L3. |
| **Applies to** | ✓ Social robot interaction · ✓ Embodied agent interaction · ⚠ General HRI (developed specifically for social robot contexts, not industrial) · ⚠ Mental-health robot context (requires pilot; MG-U9-02) |
| **What claim it can safely support** | (1) Dimension 3 (Interactive expression and information understanding) directly maps to the "information comprehension" component of RQ3 — specifically the sub-dimension of whether the robot's communicative expression was understood. This is the closest validated HRI measure to information comprehension found in the approved corpus, though it measures perceived understanding rather than objective comprehension accuracy. (2) Dimension 5 (Interaction behaviour perception) maps to "perceived naturalness" of the robot's behavior — applicable to the naturalness component of RQ3. (3) The 5-dimensional structure provides a validated framework for measuring naturalness and social presence as user-perception constructs. [L3 PENDING] |
| **What claim it cannot support** | (a) Objective information comprehension accuracy — the scale measures perceived communicative understanding, not verified recall of information content. This is a user-perception measure only. (b) Clinical rapport or therapeutic relationship — social presence perception ≠ therapeutic alliance or clinical care quality. (c) That high social presence scores predict any clinical outcome. |
| **Evaluation design relevance for RQ3** | **Naturalness and perceived information understanding measures**: (1) Administer the full 17-item scale as the primary "perceived naturalness" measure in the RQ3 user study. (2) Use Dimension 3 (Interactive expression and information understanding) as a supplementary self-report measure alongside the custom comprehension recall test (MG-U9-01), noting that Dimension 3 measures perceived understanding while the custom test measures objective recall — these are complementary, not identical. (3) Compare scores across conditions (voice-only vs. voice+gesture) on Dimensions 3 and 5 to assess whether gesture integration improves perceived information clarity and interaction naturalness. |
| **Overclaim risks** | (1) Dimension 3 perceived understanding ≠ objective comprehension accuracy — do NOT substitute the social presence scale for a comprehension test; they measure different things (perception vs. recall). (2) Full authors unconfirmed — resolve before citation. (3) Validation study details (sample, context) are unconfirmed — the scale's psychometric properties in the proposed context require verification before deployment. |
| **L1** | ✓ |
| **L2** | Partial (Nature DOI + PMC confirmed; full authors TBC) |
| **L3** | PENDING — exact item wording, validation sample characteristics, and psychometric properties require direct source verification |

---

## Safe-to-Cite Claims from U9 Adopt Group

| Claim ID | Claim text | Source | Claim type | Permitted paper section | Constraint |
|----------|------------|--------|------------|------------------------|------------|
| U9-E1 | The Godspeed Questionnaire Series provides validated semantic differential subscales for Perceived Safety, Likeability, Animacy, and Perceived Intelligence of robots. | C01 (IJSR 2009) | Measurement instrument | Background, Evaluation | Do NOT cite as clinical safety measure; perceived safety = user perception only |
| U9-E2 | Trust in robots is a multidimensional construct influenced by human factors, robot factors (especially performance), and contextual factors. | C03 (Human Factors 2021) | Theoretical framework | Background, Evaluation design framing | Trust = user perception; NOT therapeutic alliance |
| U9-E3 | Six factors associated with perceived safety in HRI include context, comfort, experience/familiarity, trust, sense of control, and transparency/predictability of robot actions. | C04 (RAS 2022) | Measurement framework | Background, Evaluation | Physical HRI context; psychological security transfer requires explicit justification |
| U9-E4 | A 2024 systematic review identified 27 validated instruments for psychological dimensions in HRI; no instrument evaluates measurement error and responsiveness in healthcare robot contexts. | C05 (JMIR 2024) | Systematic review finding | Background, Limitations | Identifies gap in clinical-context HRI psychometrics; supports MG-U9-01 and MG-U9-02 |
| U9-E5 | The Almere Model provides validated subscales for trust, anxiety, social presence, and intention to use in assistive social agent interaction with older adults. | C06 (IJSR 2010) | Measurement instrument | Background, Evaluation | Elderly care context; population transfer requires pilot; anxiety ≠ clinical anxiety disorder measure |
| U9-E6 | A 5-dimensional, 17-item Robot Social Presence scale has been developed and validated, including a dimension for perceived interactive expression and information understanding. | C07 (Sci. Reports 2023) | Measurement instrument | Evaluation | Perceived understanding ≠ objective comprehension; full authors TBC |

---

## Construct-to-Instrument Mapping Summary

| RQ3 construct | Mapped instrument(s) | Can support | Cannot support |
|---------------|---------------------|-------------|----------------|
| Perceived security | C01 (GQS Perceived Safety) + C06 (Almere Anxiety inverted) + C04 (control + transparency items adapted) | User's subjective sense of non-threat and psychological comfort | Clinical safety of the system · Clinical anxiety reduction |
| Trust | C03 (theoretical frame) + C05 (select validated instrument) | User's perceived confidence in the robot's reliability and benevolence | Therapeutic alliance · Clinical trust · That trust improvement = clinical benefit |
| Perceived naturalness | C01 (GQS Animacy + Likeability) + C07 (Interaction behaviour perception dimension) | User's perception of fluidity, human-likeness, and communicative quality | Clinical rapport · Evidence of natural care provision |
| Social presence | C07 (full scale) | User's perception of the robot as a social partner | Therapeutic companionship · Clinical care quality |
| Information comprehension (subjective) | C07 (Dimension 3: Interactive expression and information understanding) | User's perceived understanding of robot communication | Objective recall accuracy · Treatment adherence · Clinical knowledge uptake |
| Information comprehension (objective) | **[MATERIAL GAP MG-U9-01]** — custom test required | Accuracy of scenario-specific information recall | Any clinical outcome · Therapeutic adherence |
| User acceptance | C06 (Almere full model) | Behavioral intention and overall acceptance of the robot | Clinical recommendation · Clinical deployment validation |

---

## Overclaim Risk Summary (U9 Adopt Group)

| Risk | Instruments at risk | Constraint |
|------|---------------------|------------|
| Perceived safety ≠ clinical safety | C01, C04 | GQS/Rubagotti scores measure user perception, not system safety — state explicitly in Evaluation |
| Trust ≠ therapeutic alliance | C03, C06 | Almere Trust = perceived benevolence; Hancock model = HRI trust factors — neither maps to clinical therapeutic alliance |
| Anxiety subscale ≠ clinical anxiety assessment | C06 | Almere Anxiety = discomfort with technology; NOT GAD-7 or other clinical anxiety measure — must not be described in clinical terms |
| Perceived social presence ≠ quality of care | C07 | High social presence scores do not constitute evidence that the robot provides high-quality care |
| Perceived understanding ≠ objective comprehension | C07 (Dimension 3) | Subjective "felt understood" ≠ verified information recall — present both measures as complementary, not equivalent |
| Population transfer | C01, C06 | Godspeed and Almere were developed for non-mental-health contexts; transfer validity must be established via pilot testing before main study |
| Authors unconfirmed | C05, C07 | Resolve full author lists before manuscript citation |

---

## U9 Extraction Completion Status

| Paper | Extracted | L3 resolved | Full-text required |
|-------|:---------:|:-----------:|:-----------------:|
| C01 Godspeed | ✓ | No | Yes (item wording, item counts) |
| C03 Hancock 2021 | ✓ | No | Yes (meta-analysis scope, mental-health coverage) |
| C04 Rubagotti 2022 | ✓ | No | Yes (exact six-factor taxonomy, item sources) |
| C05 JMIR 2024 | ✓ | No | Yes (identify specific recommended instrument from 27 reviewed) |
| C06 Almere Model | ✓ | No | Yes (exact Trust and Anxiety item wording) |
| C07 Social Presence Scale | ✓ | No | Yes (item wording, validation sample, psychometric properties) |

**All L3 remain PENDING.** The most critical L3 action before the Evaluation section can be drafted: read C05 (JMIR 2024 systematic review) in full to identify the specific validated trust instrument from the 27 reviewed, then obtain that instrument's items via its primary source.
