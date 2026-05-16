# Related Work Draft v1 — Audit Report

**Input:** `docs/paper/related_work_draft_v1.md`
**Audit scope:** Unsupported claims · Overclaims · Clinical efficacy leakage · Perception-to-clinical overreach · Engineering-to-safety overreach · arXiv overstatement · Missing qualifiers · MATERIAL GAP justification · Downgrade/removal candidates
**Governance Layer: ACTIVE** — All findings reference claim IDs and line numbers from the draft.

**Total issues found:** 20
**Critical:** 2 · **Major:** 8 · **Minor:** 10

---

## Audit Table

| Issue ID | Section | Problematic claim (line) | Risk type | Severity | Recommended fix |
|----------|---------|--------------------------|-----------|:--------:|-----------------|
| A-01 | 2.1 (line 26) | "precluding the overlapping speech and real-time backchanneling that characterize natural conversation" — no citation | unsupported claim | Minor | Add a citation from the approved corpus (E7 survey or E5 NeurIPS system describe cascaded pipeline limitations) or rephrase as general background without citation |
| A-02 | 2.1 (line 28) | "underlying later full-duplex systems" attributes E2 (AudioLM) as the lineage for full-duplex systems broadly — the extraction limits E2's scope to "Moshi's Mimi codec," not full-duplex systems in general | overclaim | Minor | Replace "underlying later full-duplex systems" with "a principle extended in Moshi's Mimi codec" — matching the extraction's safe wording exactly |
| A-03 | 2.1 (line 28) | "it informs the Inner Monologue mechanism used in subsequent architectures" attributes E2 (AudioLM codec) as the basis for Moshi's Inner Monologue — the extraction says E2 supports the Mimi *codec* lineage only; the Inner Monologue (text prefix generation before audio tokens) is a distinct Moshi component not attributed to AudioLM in the extraction | unsupported claim | Major | Remove the "informs the Inner Monologue" clause entirely. E2 supports codec architecture lineage only. The Inner Monologue description belongs in a separate sentence about Moshi itself (E1), not as a consequence of AudioLM |
| A-04 | 2.1 (line 28) | "This semantic-before-acoustic principle substantially improves the linguistic coherence of generated speech" — "substantially" is a quantitative strength claim; the extraction marks E2 as L3 PENDING | source-status overstatement | Minor | Replace "substantially improves" with "improves" or "is reported to improve," maintaining the L3 PENDING caveat |
| A-05 | 2.1 (line 34) | "as the training corpora for speech are orders of magnitude smaller than text corpora" — no citation; not in the approved corpus | unsupported claim | Minor | Remove the specific "orders of magnitude" quantitative claim, or rephrase as "speech training data is substantially more limited than text training data" as a general statement, without citation |
| A-06 | 2.2 (line 44) | "Chen et al. demonstrated, in *the first* audio-native RAG framework (WavRAG)" — "the first" accepts the authors' own novelty self-claim without independent verification; L3 PENDING | source-status overstatement | Minor | Replace "in the first audio-native RAG framework" with "in an audio-native RAG framework (WavRAG)" and add "described by the authors as the first of its kind" if the novelty claim is to be retained |
| A-07 | 2.2 (line 46) | "exploiting the natural temporal gap between spoken response onset and informational content delivery" — this is a detailed mechanistic description of MoshiRAG (arXiv:2604.12928, under review); citing specific mechanism of an unreviewed preprint as settled architectural fact | source-status overstatement | Major | Hedge appropriately: replace with "which proposes to exploit the temporal gap between response onset and content delivery — a mechanism described in the preprint but not yet peer-reviewed" |
| A-08 | 2.3 (line 54) | "This result establishes that parallel generation of speech and gesture intent is architecturally feasible within the inference budget of *deployable robot hardware*" — generalizes from the specific Pepper/Furhat platforms tested by Galatolo & Winkle to "deployable robot hardware" broadly | overclaim | Minor | Replace "deployable robot hardware" with "the tested robot platforms (Pepper and Furhat)" or "platforms with inference budgets comparable to the tested systems" |
| A-09 | 2.3 (line 56) | "The formal properties of BTs…supporting formal state-space safety and liveness analysis" — in the context of the proposed system's BT selection, readers may interpret this as implying the *specific* BT instance for the proposed system has been formally verified; the extraction (S1) supports formal analysis as a *possible* method, not as already applied | engineering-to-safety overreach | Major | Add a qualifier: "…supporting formal state-space safety analysis *as a method available to system designers* [CRC Press, 2018]; the specific BT instance adopted in this work has not yet undergone such analysis, which is identified as future work" |
| A-10 | 2.3 (line 56) | "confirming BTs as *the dominant formalism* for modular robot behavior selection in social robot contexts" — the Iovino et al. survey (E15) documents 160+ BT papers but does not claim BTs are "dominant" in a comparative sense | overclaim | Minor | Replace "confirming BTs as the dominant formalism" with "documenting extensive adoption of BTs in robotics and AI, including social robot behavior planning" — matching the extraction's safe wording |
| A-11 | 2.3 (line 58) | "establishing a precedent for LLM-driven behavior selection in the context of HRI" — E18 has limited content confirmed from search snippets only; attributing "establishing a precedent" is a strong claim from an unverified source | source-status overstatement | Major | Replace "establishing a precedent for LLM-driven behavior selection" with "providing preliminary evidence for LLM-driven behavior generation in social robot dialogue contexts; full architectural details are pending source verification" |
| A-12 | 2.4 (line 64) | "Research on human speech-gesture synchrony has found that gesture stroke onset typically precedes the corresponding lexical affiliate in speech, facilitating listener comprehension" — no citation; this claim draws on gesture psycholinguistics literature (e.g., McNeill, de Ruiter) that is **outside the approved corpus** | unsupported claim | Critical | Remove this sentence entirely or replace with a general statement citing the BEAT taxonomy (E19) for the onset-stroke-retraction structure — which is the approved corpus's basis for gesture timing. Do not introduce out-of-corpus citations |
| A-13 | 2.4 (line 66) | "providing a timing prediction precedent *applicable to interactive robot signal dispatch*" (E21) — the qualifier is too broad; the backchannel timing distinction is stated in the next sentence, but this phrase could still be read as implying E21 is applicable to gesture command dispatch | missing qualifier | Minor | Replace "applicable to interactive robot signal dispatch" with "applicable to backchannel signal dispatch during user speech turns" — the more specific framing that anticipates and pre-empts the conflation risk |
| A-14 | 2.4 (line 68) | "This work provides *the clearest* peer-reviewed precedent for voice-and-gesture output coordination in a real dialogue robot" — "clearest" is a superlative implying a comparative evaluation of all prior systems that was not conducted; the extraction supports E20 as a peer-reviewed deployment precedent but does not rank it | overclaim | Minor | Replace "the clearest peer-reviewed precedent" with "a peer-reviewed precedent" — removing the comparative superlative |
| A-15 | 2.5 (line 78) | "The guidance establishes six principles — transparency, safety, accountability, *equity*, privacy, and sustainability" — specific principle names are cited from WHO 2024 (S2) without L3 verification; the extraction confirms "six principles" exist but does not verify the exact names | source-status overstatement | Minor | Add an L3 qualifier: "The guidance establishes six principles (exact names subject to verification from source) covering transparency, safety, accountability, equity, privacy, and sustainability [WHO, 2024]" or soften to "The guidance establishes foundational principles for responsible health AI, including transparency, human oversight, privacy, and accountability [WHO, 2024]" |
| A-16 | 2.5 (line 78) | "with human oversight identified as *non-negotiable* for high-stakes interactions" — "non-negotiable" is stronger language than the extraction supports for S2; the extraction says human oversight is "required," not "non-negotiable" | overclaim | Minor | Replace "non-negotiable" with "mandatory" or "a foundational requirement" — matching the extraction's language |
| A-17 | 2.5 (line 80) | "is *established* in a 2025 high-impact study [Nat. Med., 2025] (S6)" — S6's full content is explicitly flagged as unconfirmed in the extraction and claim-citation matrix; claiming it "establishes" a specific finding is a source-status overstatement from an unconfirmed source | source-status overstatement | Major | Replace "is established in a 2025 high-impact study [Nat. Med., 2025]" with "has been argued in a 2025 study pending full verification [Nat. Med., 2025]" — hedging appropriately given the unconfirmed source content |
| A-18 | 2.5 (line 80) | "grounding the human-in-the-loop requirements at *Tier 3* of the proposed safety architecture" — "Tier 3" is design terminology from the proposed system's safety taxonomy; introducing it in the Related Work section is premature; Related Work should position relative to prior work, not introduce the proposed system's internal design vocabulary | missing qualifier | Minor | Remove "at Tier 3 of the proposed safety architecture" from this sentence; move this system-design link to the System Design section where Tier 3 is formally defined |
| A-19 | 2.6 (line 88) | "Full-duplex spoken language models *have reached* interactive latency targets" — stated as settled fact; the primary latency evidence is E1 (Moshi, arXiv) which is an unreviewed preprint; the only peer-reviewed latency figure is E5 (NeurIPS 2024, <500ms in >50% of interactions) which is context-specific | source-status overstatement | Major | Qualify: "Recent work suggests full-duplex spoken language models can approach interactive latency targets [NeurIPS 2024; arXiv:2410.00037]" — not "have reached" |
| A-20 | 2.6 (line 88) | "Behavior Trees provides modularity and *formal safety analyzability* over predefined command vocabularies" — same engineering-to-safety overreach as A-09; "formal safety analyzability" in the integration gap summary implies the proposed system's BT is formally verified | engineering-to-safety overreach | Major | Replace "formal safety analyzability" with "support for formal safety analysis" or "formal analyzability in principle" — preserving the correct claim that BTs as a formalism support formal analysis without implying the specific instance is verified |

---

## MATERIAL GAP Marker Justification Audit

| Marker | Location | Is the gap justified? | Notes |
|--------|----------|-----------------------|-------|
| MG-01 | §2.2, line 46 | ✓ Justified | Correctly flags MoshiRAG as unreviewed; placement is appropriate |
| MG-02 | §2.2, line 46 | ✓ Justified | Correctly flags the absence of a peer-reviewed async RAG category |
| MG-03 | §2.3, line 58 | ✓ Justified | Correctly identifies the primary engineering novelty for RQ2 |
| MG-04 | §2.3, line 58 | ✓ Justified | Correctly identifies the unified architecture gap |
| MG-05 | §2.4, line 68 | ✓ Justified | Correctly flags the absence of a full-duplex timing model |
| MG-07 | §2.4, line 68 | ✓ Justified | Correctly flags the half-duplex evidence base limitation |
| MG-08 | §2.5, line 82 | ✓ Justified | Correctly flags the absence of a voice/embodiment safety framework |
| MG-09 | §2.5, line 82 | ✓ Justified (content), but **formatting inconsistency** | MG-09 appears as inline `[MATERIAL GAP MG-09]` without bold formatting, inconsistent with MG-08 and MG-10 which use bold. Additionally, MG-09 in the related work section is a scope limitation, not an architectural gap — consider moving to Limitations section in the final draft |
| MG-10 | §2.5, line 82 | ✓ Justified | Correctly flags the absence of gesture safety standards |
| MG-06 | Not marked | ✓ Correct absence | MG-06 is a citation hygiene rule, not a content gap; correctly absent from inline markers |
| MG-11 | Not marked | ✓ Correct absence | MG-11 belongs in the Evaluation section, not Related Work |
| MG-12 | Not marked | ✓ Correct absence | MG-12 is handled by the governance annotation table |

---

## Claims Recommended for Downgrade, Narrow, or Removal

| Claim | Action | Reason |
|-------|--------|--------|
| "informs the Inner Monologue mechanism used in subsequent architectures" (line 28, A-03) | **Remove** | E2 (AudioLM) supports the Mimi codec lineage only; the Inner Monologue is a separate Moshi component not attributed to AudioLM in the extraction |
| "Research on human speech-gesture synchrony has found that gesture stroke onset typically precedes the corresponding lexical affiliate in speech, facilitating listener comprehension" (line 64, A-12) | **Remove** | No citation; out-of-corpus; cannot be supported by the approved literature |
| "Full-duplex spoken language models have reached interactive latency targets" (line 88, A-19) | **Downgrade** | Change to "can approach" or "recent work suggests" — primary evidence is arXiv |
| "establishing a precedent for LLM-driven behavior selection" (line 58, A-11) | **Narrow** | Change to "providing preliminary evidence" with verification caveat |
| "the clearest peer-reviewed precedent" (line 68, A-14) | **Narrow** | Remove superlative; change to "a peer-reviewed precedent" |
| "Tier 3 of the proposed safety architecture" (line 80, A-18) | **Remove from Related Work** | Move to System Design section; premature use of proposed system terminology |
| "formal safety analyzability" (lines 56 and 88, A-09, A-20) | **Narrow both instances** | Add "in principle" or "as a method available to designers" to distinguish the formalism's property from the specific instance's verification status |

---

## Summary by Risk Type

| Risk type | Issue count | Highest severity |
|-----------|:-----------:|:----------------:|
| Unsupported claim | 4 (A-01, A-03, A-05, A-12) | Critical (A-12) |
| Overclaim | 5 (A-02, A-08, A-10, A-14, A-16) | Minor |
| Source-status overstatement | 6 (A-04, A-06, A-07, A-11, A-15, A-17, A-19) | Major |
| Engineering-to-safety overreach | 2 (A-09, A-20) | Major |
| Missing qualifier | 3 (A-13, A-15, A-18) | Minor |
| Clinical efficacy leakage | 0 | — |
| Perception-to-clinical overreach | 0 | — |
| Material gap issue | 1 (MG-09 formatting) | Minor |

**Clinical efficacy leakage: NONE FOUND.** The draft correctly maintains the engineering framing throughout and does not import clinical outcome claims.

**Perception-to-clinical overreach: NONE FOUND.** P1 (backchannel timing → perceived engagement) is correctly handled as a user-perception claim with no extension to clinical benefit.

---

## Priority Fix Order

Address in this sequence before v2 draft:

1. **[Critical] A-12** — Remove out-of-corpus claim about human speech-gesture synchrony (line 64)
2. **[Major] A-03** — Remove "informs the Inner Monologue mechanism" attribution to AudioLM (line 28)
3. **[Major] A-09** — Add "in principle / available to designers" qualifier to BT formal safety claim (line 56)
4. **[Major] A-17** — Downgrade S6 from "established" to "argued, pending verification" (line 80)
5. **[Major] A-11** — Downgrade E18 from "establishing a precedent" to "providing preliminary evidence" (line 58)
6. **[Major] A-07** — Hedge MoshiRAG mechanism description as preprint claim (line 46)
7. **[Major] A-19** — Downgrade "have reached" to "recent work suggests" for latency claim (line 88)
8. **[Major] A-20** — Add "in principle" to "formal safety analyzability" in integration gap (line 88)
9. **[Minor] A-14** — Remove superlative "clearest" from E20 (line 68)
10. **[Minor] A-18** — Remove "Tier 3 of the proposed safety architecture" from Related Work (line 80)
11. Remaining minor issues (A-01, A-02, A-04, A-05, A-06, A-08, A-10, A-13, A-15, A-16) — address in final polish pass
