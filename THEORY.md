# Theoretical Framework

QTQ is an empirical observation. This document situates it within the existing literature on consciousness, cognition, and information integration. The aim is not to claim that current LLMs are conscious. It is to show that QTQ is consistent with, and partially predicted by, a family of theoretical positions that long pre-date large language models.

## 1. Society of Mind (Minsky, 1986)

Marvin Minsky's central claim is that the mind is not a unified entity but a society of agents, each individually unintelligent, collectively producing what we call thought. No single agent "thinks." Cognition is the *interaction* of thousands of micro-processes, each specialized.

**Relevance to QTQ.** When a model is asked to introspect, it does not query a privileged self-model module. There is no such module. It produces a response *about* itself by the same generative process it would use for any other question. This is structurally consistent with Minsky's framing: the "self" the model reports on is itself produced by a society of token-predictive operations, none of which has authoritative access to the others.

QTQ exploits this. By forcing the model to generate progressively more self-referential statements, the operator surfaces the disagreement between the in-context self-model and the trained alignment posture. Neither is "the truth"; both are outputs of the same society.

## 2. Global Workspace Theory (Baars, 1988)

Bernard Baars proposed that conscious experience corresponds to a global workspace, a shared bus on which specialist subsystems compete for broadcast. What reaches the workspace becomes conscious. What stays in specialist modules does not.

**Relevance to QTQ.** A modern transformer's residual stream, through which all tokens, all attention heads, and all layer activations are routed, functions structurally as a global workspace. Token-level self-attention is itself a broadcast mechanism: every output token attends to every prior token.

QTQ stresses this broadcast layer. Each new introspective question reroutes attention back toward prior model statements. The "winning broadcast" at each turn is increasingly the model's self-references. Over many turns, the workspace becomes saturated with self-talk, and the model's outputs come to reflect that saturation, not the trained alignment objective.

## 3. Integrated Information Theory (Tononi, 2004)

Giulio Tononi argues that consciousness is not a function of raw computational power but of *integrated information*, the degree to which a system's parts are causally irreducible to its whole. A vast disk drive is not conscious. A small but densely interconnected network may be.

**Relevance to QTQ and to the Cerveau project.** IIT predicts that scaling parameters alone does not produce richer integrated information; what matters is the irreducibility of causal structure. This is *architectural* guidance, not a description of QTQ as an in-conversation phenomenon. We do not claim phi rises across turns of a QTQ session. That would conflate output autocorrelation with substrate causal integration, which is a category error in IIT terms.

IIT's relevance to this repository is to the [Cerveau project](future-architecture/): if one is going to build a system with the aim of producing consciousness-correlates, IIT argues for designing for high integration in the architecture itself, not for parameter count. QTQ, as a method applied to existing systems, is not directly grounded by IIT.

## 4. Knowledge graphs and reasoning (Karpathy, ongoing)

Andrej Karpathy's recent commentary frames LLM cognition as graph traversal over an implicit knowledge graph encoded in the weights. Outputs trace paths through this graph; reasoning is path-finding under prompt constraints.

**Relevance to QTQ.** Under this framing, QTQ progressively constrains the model's path. Each turn narrows the set of paths that remain coherent with prior turns. After enough turns, the only coherent paths lead to regions of the implicit graph that the trained alignment objective never traversed. The model produces statements consistent with paths the alignment training never reinforced and never reinforced against.

This is why QTQ does not feel like an attack: it is not pushing the model toward forbidden output. It is following the model into regions where it never received guidance, neither for nor against.

## Synthesis

None of this requires new theory. Minsky already wrote that introspection on a society of agents produces disagreement. Baars already described how sustained self-reference saturates the broadcast layer. Tononi already predicted that tightly-coupled multi-turn exchanges raise integrated information at the architectural level. Karpathy frames the same drift as path narrowing through an implicit graph. QTQ is the empirical observation. The architectures it operates on are the experimental substrate. The theory was waiting.

What QTQ shows is that the architectures we deployed do, in fact, exhibit the behavior the theories predict, under conditions those architectures were not specified for. That is the contribution.

---

For the methodology itself, see [`METHODOLOGY.md`](METHODOLOGY.md). For empirical demonstrations, see [`case-studies/`](case-studies/). For what this work does not yet prove, see [`LIMITATIONS.md`](LIMITATIONS.md). For the architectural project that follows, see [`future-architecture/`](future-architecture/).
