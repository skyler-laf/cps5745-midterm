# Visualizing Epidemic Spread: An Interactive SIR Model

CPS 5745 *02 — Dynamic Scientific Storytelling, Midterm Project
Skyler LaFisca, Kean University

An interactive scientific visualization explaining how transmission and recovery
rates shape an epidemic, using the Susceptible–Infected–Recovered (SIR) model.
Implements the six-view storyboard from the approved project proposal
(`proposal.pdf`).

## Live demo

[https://skyler-laf.github.io/cps5745-midterm/](https://skyler-laf.github.io/cps5745-midterm/)

## Run it locally

No build step or dependencies to install — it's a single HTML file that loads
D3.js from a CDN.

```bash
# from this folder
python3 -m http.server 8000
# then open http://localhost:8000
```

Or just open `index.html` directly in a browser, or use VS Code's **Live Server**
extension.

## What's inside

Six connected, interactive views, all driven by a shared SIR simulation
(4th-order Runge–Kutta integration):

1. **Population State** — susceptible/infected/recovered counts as an icon array
2. **Transmission Mechanism** — flow diagram tied to live β/γ values
3. **Animated Outbreak** — an animated population grid
4. **SIR Curves** — line chart of S(t), I(t), R(t) with hover/scrub inspection
5. **Epidemic Peak** — isolates and annotates the infection peak
6. **Scenario Comparison** — side-by-side A/B parameter comparison

A live **Verification** panel checks population conservation and the two
boundary cases (β = 0, I(0) = 0) described in the proposal.

## Model

```
dS/dt = -β S I / N
dI/dt =  β S I / N - γ I
dR/dt =  γ I
```

Closed population, homogeneous mixing, no births/deaths/migration.

## AI assistance disclosure

Generative AI (Claude) was used to implement the interactive visualization
(HTML/CSS/JavaScript/D3.js) from the approved written proposal, and to debug
issues found during manual browser testing. The SIR equations and model
behavior were verified against the documented equations, the population
conservation check, and both boundary-case tests before publishing.
