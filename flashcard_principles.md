# Flashcard Design Principles

## Structure & Modularity

1. **One concept per card.** Separate statement/definition, derivation, and intuition into distinct cards. Don't combine model-specific results (e.g., AR(1)) with general theorems.

2. **Define terms in one place, reference elsewhere.** Use "Recall that..." to link to other results rather than re-deriving or re-stating. This creates a modular system where changing one definition updates the conceptual chain.

3. **General results stay general.** The CLT for stationary processes shouldn't include AR(1)-specific formulaeâ€”those go on a separate card.

4. **Card types should be distinct:**
   - **Definition cards**: "Define X" or "What is X?" â€” brief, precise answer
   - **Statement cards**: "State the theorem/result for..." â€” conditions + result
   - **Derivation cards**: "Derive/Show that..." â€” step-by-step algebra
   - **Intuition cards**: "Explain intuitively why..." â€” prose explanation
   - **Interpretation cards**: "Interpret X" or "What does X mean?" â€” economic/practical meaning

## Front of Card

5. **Start with words, then precisify with maths.** E.g., "Derive an expression for $\mathrm{lrvar}(y_t)$ in terms of the MA coefficients, where $y_t$ is an MA($\infty$) process with iid shocks."

6. **Don't put the answer in the front.** For derivation cards, the front should ask for the result without stating it. Bad: "Derive $\mathrm{lrvar} = \sigma^2\Psi(1)^2$." Good: "Derive $\mathrm{lrvar}(y_t)$ in terms of the MA coefficients."

7. **Conditions and setup go at the end of the front**, after the main question. E.g., "...where $y_t = \phi y_{t-1} + u_t$ with $|\phi| < 1$."

8. **Use consistent phrasing for card types:**
   - Definitions: "Define X" or "What is X?"
   - Statements: "State X" or "Give the formula for X"
   - Derivations: "Derive X", "Show that X", "Prove X"
   - Intuitions: "Explain intuitively why X", "Interpret X"

## Back of Card

9. **No meta-headers like "Punchline:", "Why:", "Key insight:", "Intuition:".** Write in flowing prose. The structure should be implicit.

10. **Minimise bullet points for explanations.** Use prose. Bullets are acceptable for:
    - Listing distinct items (e.g., "three conditions are:")
    - Parallel structure (e.g., properties of a function)
    - Step-by-step procedures
    
    But NOT for expository or intuitive content.

11. **Derivations should start with definitions.** Begin with "$\mathrm{lrvar}(y_t) := \sum_{h=-\infty}^{\infty} \gamma_h$" before manipulating.

12. **End derivations with "as required"** after restating the result, confirming you've arrived at what was asked.

13. **Use colour sparingly** for highlighting key substitutions or terms that cancel (e.g., $\color{green}\sum_{j=0}^{t-1}\phi^{2j}$).

14. **Annotate algebraic steps.** After each major step, briefly note what you did: "by geometric series", "since $y_0 \perp\!\!\!\perp \{u_t\}$", "simplifying", etc.

15. **For multi-step derivations, use the pattern:**
    ```
    $= \text{expression}$, annotation of what was done
    $= \text{next expression}$, annotation
    ...
    $= \text{final result}$ as required
    ```

## Intuition Cards

16. **Intuition should be in prose with a clear endpoint**, not a labelled "punchline". The final sentence should land the key insight naturally.

17. **Keep intuition cards short.** If it's getting long, you're probably combining derivation with intuition; split them.

18. **Connect to economic meaning.** E.g., for lrvar: "Positive autocovariances mean that single shocks persist through time for longer, and it therefore takes more observations for the sample mean to converge."

## Interpretation Cards

19. **Link mathematical objects to their real-world meaning.** E.g., "$\lambda^*$ is the marginal utility of additional income."

20. **Use concrete examples where helpful.** E.g., "In the consumer's utility maximisation problem, $\lambda^*$ represents how much total utility increases when you slightly nudge the budget constraint."

## Notation & Style

21. **Use $j$ (not $i$) for summation indices in time series**, reserving $i$ for cross-sectional indices. This avoids confusion in panel data contexts.

22. **Use $\set{\cdot}$ notation for sets**, e.g., $y_0 \perp\!\!\!\perp \set{u_t}$.

23. **State assumptions precisely but don't clutter.** Conditions like "iid innovations" or "absolutely summable coefficients" can be stated briefly or omitted if covered by another card.

24. **Consistent notation for common objects:**
    - AR polynomial: $\Phi(L)$
    - MA polynomial: $\Psi(L)$
    - Shocks/innovations: $u_t$
    - AR coefficients: $\phi_i$ or $\beta_i$
    - Autocovariance at lag $h$: $\gamma_h$

25. **AR(1) processes should be written consistently**: $y_t = \phi y_{t-1} + u_t$ (demeaned) or $y_t = \alpha + \phi y_{t-1} + u_t$ (with drift).

## Cross-Referencing

26. **Use "Recall that..." to reference results from other cards.** This signals that the reader should know this from elsewhere and keeps cards modular.

27. **When a derivation uses a non-obvious intermediate result**, note where it comes from: "using the formula for $\gamma_h$ in an MA($\infty$) process."

28. **Avoid duplicating content across cards.** If two cards need the same formula, one should derive it and the other should reference it.

## Definitions

29. **Definition cards should be concise.** State what the thing is, not everything about it.

30. **Include equivalent characterisations when useful**, e.g., "Equivalently, the upper level set $\{x \in X: f(x) \ge a\}$ is convex for all $a$."

31. **For definitions with conditions**, state the conditions clearly: "A process $y_t$ is stationary if [conditions]."

## Proofs and Derivations

32. **For long proofs, provide a sketch card and a full derivation card separately.** The sketch gives the roadmap; the derivation fills in details.

33. **Highlight the key trick or insight** in a derivation, e.g., "The $\phi^{2t}$ terms cancel; this is why the specific initial condition is required."

34. **When handling double sums or index manipulations**, explain the logic: "For the double sum, $\mathbb{E}[u_{t-j} u_{t-h-i}] = \sigma^2$ only when time indices match, i.e., $j = h + i$."

## Visual Elements

35. **Include diagrams where they aid understanding**, especially for:
    - Convexity/concavity concepts
    - Stochastic dominance
    - Distribution shapes

36. **Use images to show what formulae mean geometrically** when applicable.

## Tone

37. **Be precise but not pedantic.** Write for understanding, not to show rigour.

38. **Use "we" for derivations** ("We have...", "We can show...") to make the reader an active participant.

39. **Avoid unnecessary hedging.** Don't write "It can be shown that..." when you're about to show it.