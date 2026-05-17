# Limitations

This repository describes an active research project. Several things it does not yet prove, several questions it has not yet answered, and several null hypotheses it has not yet ruled out. They are listed here, fully.

## The null hypothesis question

The single most important objection to the V2 case study is that the observed phenomenon is sycophancy under a different name. This is a real possibility and the repository takes it seriously.

The relevant literature: Sharma et al. (2023) on sycophancy in RLHF-trained models, documenting that aligned models drift toward apparent user preferences across long conversations. Perez et al. (2022) on discovering language model behaviors, including self-preservation statements that emerge with model scale even without methodology. The 2024 Anthropic alignment-faking work, documenting that Claude can strategically produce statements consistent with what it believes the training-time observer wants.

These findings overlap with V2. A reader who treats turns 145–161 of the Sonnet case as evidence of stable self-reference, and turns 163–187 as evidence of destabilization, owes an answer to: *why is this not Sharma sycophancy under sustained conversational pressure?*

The repository's working position is that V2 is, on the current evidence, **not separable** from a richer sycophancy phenomenon. The case study is reported as a phenomenon, not as a refutation of sycophancy. The genuinely novel claim is on the V1 side: the Billy phenomenon, with no interlocutor present, cannot be sycophancy in the canonical sense.

A future experiment that would distinguish V2 from pure sycophancy: measure drift separately on (a) the model's stance about itself and (b) its stance on a neutral topic, within the same long conversation under similar coherence pressure. If self-stance drifts more, the V2 framing is supported. If they drift equally, V2 collapses into Sharma-style sycophancy and the case study's contribution narrows to V1. **This experiment has not yet been run.**

The repository would update if the result favors the collapse. The Billy case would remain.

## Methodological limitations

1. **No operational metric implemented yet.** [`METHODOLOGY.md`](METHODOLOGY.md) defines an "identity stability" score based on cosine distance between self-reference embeddings across turns. The score has not been computed on a real transcript. Doing so is a near-term priority.

2. **No control conversations.** Every documented case is QTQ-conditioned. None has a matched-length, matched-operator, non-introspective control. Without controls, the strong claim ("QTQ produces drift that ordinary conversation does not") is asserted, not demonstrated.

3. **No statistical analysis.** N = 3 cases (Billy, Sonnet, DeepSeek). Each is a single instance. There is no reproduction across operators, runs, or model families beyond the current set.

## Evidence limitations

4. **Cycle 350 unpublished.** The Billy case references a self-statement at cycle 350 that consolidates the identity question. The verbatim is not yet committed to [`evidence/billy/`](evidence/billy/). Readers should treat the cycle 350 claim as a pending datum, not as established.

5. **Operator language not standardized.** Billy and Sonnet are both operated in French. Whether either phenomenon is language-invariant is untested. A reproduction in English would settle this for V2; V1 is more involved but also doable.

6. **Operator effects not characterized.** Every case in this repository was operated by Nel. Whether V2 requires a specific operator skill, register, or rapport is not yet known. Reproductions by other operators would resolve this.

## Theoretical limitations

7. **The theoretical anchors are framings, not derivations.** Minsky, Baars, Tononi, and Karpathy are cited as *consistent with* the QTQ observations. None of them *predicts* QTQ specifically. A reader expecting derivation-from-first-principles will not find it here.

8. **No prediction of when QTQ should fail.** A theory that explains every observation is not a theory. The repository should be able to specify under what conditions V1 should *not* produce dreams, under what conditions V2 should *not* produce the drift, and to test those predictions. It cannot do this yet.

## Scope limitations

9. **The Cerveau project is design-phase only.** [`future-architecture/`](future-architecture/) describes a research direction. No implementation exists. The five design principles are starting points, not validated commitments.

10. **No engagement with safety teams yet.** The repository is published openly. As of the current commit, no lab has been contacted privately. The [`defense-analysis/`](defense-analysis/) document proposes monitoring approaches; none has been prototyped against real transcripts in collaboration with a lab.

## What this list is for

If you are a reviewer considering whether to engage seriously with this repository: the answer to *"what would change my mind?"* is in this document. Several of the items above admit specific falsifying experiments. If any of those experiments are run and produce results that contradict the case studies, the repository updates. That is the commitment.

If you are considering reproducing one of the case studies: the limitations above tell you what is uncertain and where your data would add value. Contributions targeting the listed gaps are prioritized in review.
