---
title: Introduction to Transcription Networks
author: Prasoon Pandey
date: '2026-05-31'
slug: introduction-to-transcription-networks
abstract: Notes on Chapter 1
---

This is the first post in the series on systems biology. In this post, we will discuss the basics of transcription networks and how they are used to solve what Alon calls the "cognitive problem" of the cell.

# DNA, Genome, and Genes - What is the Difference?

These three terms are heard quite frequently in the biological sciences, and most of the time they are used interchangeably. However, they are different concepts and have different meanings but can be put under the same umbrella. The purpose of this section is to develop a sense of what they are and their relationship. We need to think of them not as a chain but as nested levels of organization.

## DNA

Every cell contains a coding material that is called DNA. It is a double helix structure composed of two strands of nucleotides. Each nucleotide is composed of a sugar, a phosphate group, and a nitrogenous base. The four nitrogenous bases are adenine (A), thymine (T), cytosine (C), and guanine (G). These bases pair up to form the double helix structure. It is this material that contains the genetic (or biological) information of an organism.

## Genome

Now, the genome is not a separate thing from DNA; it is the **complete collection** of all the DNA in a cell, organised into a structure called the chromosomes. In humans, we have 46 chromosomes which contain about 3 billion base pairs of DNA in total.

This genome is the **full instruction manual** for an organism. It contains the instructions for how to build and function the organism.

## Genes

A gene is a specific functional region of the DNA within the genome that encodes instructions for building a specific protein. Here is where things get interesting: Humans have approximately 20,000 genes which makes about 2% of the entire genome. The rest includes regulatory regions that control when genes turn on and off, repetitive sequences, and large stretches whose function is still not fully understood.

I have added a figure below to properly illustrate all the layers. 
<!-- {{< blog-row >}}
{{< blog-fig src="imgs/gene_genome_dna.jpg" alt="DNA double helix" caption="DNA: the double helix that stores genetic information." >}}
{{< blog-fig src="imgs/gene_genome_dna.jpg" alt="Genome and genes" caption="Genome and genes: nested levels of organization within DNA." >}}
{{< /blog-row >}} -->

![DNA_genome_gene](imgs/gene_genome_dna.jpg 'Source: https://www.cbehx.co.uk/')

# The Cognitive Problem of the Cell

This phrase was popularised by Uri Alon in his book. Traditionally, biology looked at cells through a purely biochemical lens: a signal hits a receptor, a cascade of proteins shifts, and a gene gets turned on. It sounds like simple dominoes knocking each other over.

However, Alon looked at a single cell (like an E. coli bacterium) from an **engineering and physics perspective**, where it is essentially dealing with a fundamental computation problem. It lives in a highly unpredictable environment where making a mistake means death. It has to look at the world, compute an answer, and make a choice.

Instead of thoughts, the cell uses **Transcription Factors (TFs)** as physical symbols to represent the outside world.

- When a specific sugar is outside the cell, a specific TF rapidly flips from an "inactive" to an "active" molecular shape.
- These TFs bind to DNA, acting exactly like biological logic gates (AND, OR, NOT).
- The network integrates these inputs to calculate the precise rate of protein production needed.

This is a very simplified view of the problem, but it captures the essence of what Alon is trying to say. The cell is not just a bunch of chemicals reacting with each other, it is a complex network of interactions that is trying to compute a solution to a problem.

# Transcription Networks

This is heart of our discussion in this post. The problem of the cell described above - the challenge of sensing, filtering noise, and making decision - is solved through transcription networks. While the "problem" gives us the abstract logical framework, transcription networks give us the actual structural map of how these TFs and genes are physically wired together.

To understand how this biological circuit executes its programming, we must look at the physical mechanics under the hood. This brings us to the foundation of all modern molecular biology: the **Central Dogma**.

## Central Dogma

The Central Dogma describes the one-way flow of biological information inside a cell. If the genome is the master instruction manual, the cell cannot use it directly to perform actions. It must translate that static code into physical, working proteins. This happens in two functional steps:

1. **Transcription**: The gene is copied into **a disposable mRNA molecule** by a protein machine called RNA polymerase (RNAp), a process called transcription.
2. **Translation**: The mRNA is translated into a protein by a protein machine called ribosome, a process called translation.

So the flow is: DNA → mRNA → Protein. Clean, directional, irreversible!

**Problem:** The cell has roughly 20,000 genes. It cannot transcribe all of them at full rate all the time. This would be energetically ruinous, and more importantly, wrong. An E. coli has no business producing lactose-digesting enzymes when there is no lactose in the environment. **The cell needs a way to control which genes get transcribed, when, and at what rate.** The Central Dogma tells us the direction of information flow; it says nothing about how that flow is gated.

To understand the gating mechanism, we need to look more closely at the physical structure of a gene itself.

## Gene Structure and Rate Control

The gene on the DNA is physically divided into two functional regions:
1. **Promoter**: The rate at which the gene is transcribed, the number of mRNA produced per unit time, is controlled by a regulatory region of DNA that precedes the coding region, called the promoter.
2. **Coding**: This is the actual genetic code that holds the instructions for making a protein. It is the region of the gene that is responsible for the translation of the gene.

The promoter region in itself has a small region (a specific DNA sequence) called the *binding site* (see figure below) where RNAp binds (or docks) then it slides down the coding region and copies the genetic code into an mRNA molecule. The tighter the chemical affinity between RNAp and this binding site, the more frequently RNAp lands and therefore the higher the transcription rate.

![transcription_translation](imgs/transcription_translation.png 'Source: Alon, U. (2019). An Introduction to Systems Biology: Design Principles of Biological Circuits (2nd ed.). Chapman and Hall/CRC. https://doi.org/10.1201/9780429283321')

The promoter essentially acts as switch that controls the flow of information dynamically, in response to the environment. *This is precisely where TFs come in.*

## Transcription Factors

A Transcription Factor is a specialized protein floating around inside the cell. It has a highly specific shape that allows it to grip onto the binding site in a gene's promoter — and in doing so, it either helps RNAp bind (activation) or blocks it from binding (repression).

Crucially, TFs are not static. They exist in two states, and the environment determines which state they are in:

- **Inactive State**: The TF is shaped in a way that it cannot bind to the DNA. It just floats around aimlessly.
- **Active State**: An environmental signal (like a sugar molecule binding to it, or a phosphate group being attached due to stress) causes the TF to instantly snap into a new physical shape. Now, it is "sticky" for its specific DNA target.

This is the cell's sensing mechanism. Environmental signals are converted into TF activity states, which in turn control the rate at which specific genes are expressed.

![Transcription Networks](imgs/transcription_network.png 'Source: Alon, U. (2019). An Introduction to Systems Biology: Design Principles of Biological Circuits (2nd ed.). Chapman and Hall/CRC. https://doi.org/10.1201/9780429283321')

The figure above illustrates this idea of a transcription network: **TF proteins are themselves encoded by genes, which are regulated by other TFs, which in turn may be regulated by yet other TFs, and so on.** This recursive web of interactions — TFs regulating genes that produce more TFs — is precisely what we call a transcription network.

# Mathematical Formulation

We now have the structural idea of how the transcription network is wired together. Now what we need is a quantitative framework which describes how the network behaves. 

In the network described above, the nodes are genes and arrows represent transcriptional regulation of one gene by the protein product of another gene. An arrow $X \rightarrow Y$ means that the product of gene $X$ is a transcription factor protein that can bind the promoter of gene $Y$ to control the rate at which gene $Y$ is transcribed. The number of molecules of protein $Y$ produced per unit time is a function of the concentration of $X$ in its active form, $X^*$:

$$
\begin{equation}
\frac{dY}{dt} = f(X^*) 
\tag{1}
\end{equation}
$$
where $f$ is an *input function* that describes the relationship between the concentration of $X$ in its active form, $X^*$, and the production rate of protein $Y$. This should typically be a monotonic function either increasing or decreasing for activation or repression respectively. A very typical choice for the input function is the Hill function:
$$
\begin{equation}
f(X^*) = \frac{X^*}{K_d + X^*}.
\tag{2}
\end{equation}
$$

For transcription networks specifically, this takes the form for activators:

$$
\begin{equation}
f(X^*) = \beta \frac{X^{*n}}{K^{n} + X^{*n}}.
\tag{3}
\end{equation}
$$

where we have following three parameters:
- $K$ is the **activation coefficient**, and has the units of concentration. It defines the concentration of active $X$ needed to significantly activate expression.
- $n$ is the **Hill coefficient** which is a measure of the steepness of the curve.
- $\beta$ is the **maximal promoter activity** which is reached at high activator concentrations, $X^* \gg K$ because at high concentrations, $X^*$ binds the promoter with high probability and stimulates RNAp to produce many mRNAs per unit time.

**IMPORTANT:** For repressors, the input function is:
$$
\begin{equation}
f(X^*) = \frac{K^{n}}{K^{n} + X^{*n}}.
\tag{4}
\end{equation}
$$

## Logic Input Functions

Sometimes, it's much more useful to approximate the input functions with logical approximations. For example, this could be a step function (the limiting case of the Hill function when $n \to \infty$).

$$
\begin{equation}
f_{\text{activator}}(X^*) = \begin{cases}
0 & \text{if } X^* < K \\
\beta & \text{if } X^* \geq K
\end{cases}
\tag{5}
\end{equation}
$$

Similarly, for repressors, we can use a step function:

$$
\begin{equation}
f_{\text{repressor}}(X^*) = \begin{cases}
\beta & \text{if } X^* < K \\
0 & \text{if } X^* \geq K
\end{cases}
\tag{6}
\end{equation}
$$

## Dynamics of Simple Regulation

Now that we have the mathematical framework, we can start to explore the dynamics of the transcription network. Just like any other dynamical system, we begin by properly laying out the information regarding the system. We will start with a simple case of a single gene regulated by a single transcription factor.

Consider a gene that is regulated by a TF with no additional inputs (or with all other inputs and post-transcriptional modes of regulation held constant over time). This transcription interaction is described in the network by $X \rightarrow Y$ which reads "transcription factor $X$ regulates gene $Y$." Once $X$ becomes activated by a signal, $Y$ concentration begins to change. Let us calculate the dynamics of the concentration of the gene product, the protein $Y$ and its response time.

![tf_activators](imgs/tf_activator.png 'Source: Alon, U. (2019). An Introduction to Systems Biology: Design Principles of Biological Circuits (2nd ed.). Chapman and Hall/CRC. https://doi.org/10.1201/9780429283321')

In the absence of its input signal, transcription factor $X$ is inactive and $Y$ is not produced. When the signal $S_X$ appears, $X$ rapidly transits to its active form $X^*$ and binds the promoter of gene $Y$. Gene $Y$ begins to be transcribed, and the mRNA is translated, resulting in accumulation of protein $Y$. The cell produces protein $Y$ at a rate $\beta$ (units of concentration per unit time).

$$
\begin{equation}
\frac{dY}{dt} = \beta
\tag{7}
\end{equation}
$$

Now, we will add another layer: The production of Y is balanced by two processes, protein degradation (its specific destruction by specialized proteins in the cell) and dilution (the reduction in concentration due to the increase of cell volume during growth). The degradation rate is $\alpha_{deg}$, and the dilution rate is $\alpha_{dil}$, giving a total removal rate (in units of 1/time) of

$$
\begin{equation}
\alpha = \alpha_{deg} + \alpha_{dil}
\tag{8}
\end{equation}
$$

The change in the concentration of $Y$ is due to the difference between its production and removal, as described by a dynamic equation:

$$
\begin{equation}
\frac{dY}{dt} = \beta - \alpha Y
\tag{9}
\end{equation}
$$

The removal term in the equation $\alpha Y$ is equal to the concentration $Y$ times the probability per unit time that each protein $Y$ is removed, $\alpha$.

From the equation (9), we can solve for the steady state concentration $Y_{\text{steady}}$:
$$
\begin{align}
\frac{dY}{dt} &= 0 \\
Y_{\text{steady}} &= \frac{\beta}{\alpha}
\end{align}
$$

The solution to the equation (9) is:
$$
\begin{equation}
Y(t) = Y_{\text{steady}}(1 - e^{-\alpha t})
\tag{10}
\end{equation}
$$

An important measure for the speed at which $Y$ levels change is the response time. The response time, $T_{1/2}$, is defined as the time to reach halfway between the initial and final levels in a dynamic process.

We can solve for the response time $T_{1/2}$ by solving the equation (10) for $t$ and setting $Y(t) = Y_{\text{steady}}/2$:

$$
\begin{equation}
T_{1/2} = \frac{\ln 2}{\alpha}
\tag{11}
\end{equation}
$$

WHAT? **This is a very interesting result.** Notice that $\beta$ (the production rate) completely vanished. If a cell wants to reach its destination twice as fast, it cannot achieve this by simply manufacturing the protein faster (increasing $\beta$). If it increases $\beta$, it will certainly rise faster initially, but it also raises the destination height ($Y_{\text{steady}} = \beta / \alpha$), meaning it still takes the exact same amount of time to reach the halfway point of that new, taller hill. The only way a simple gene circuit can speed up its response time is by increasing $\alpha$—meaning it must **actively destroy the protein faster or divide faster**.

## The Structural Speed Limit: Stable Proteins and Cell Generation

This dependency on the removal rate $\alpha$ exposes a fundamental physical bottleneck for the cell when we look at **stable proteins**—proteins that the cell does not actively destroy ($\alpha_{\text{deg}} = 0$). 

For stable proteins, the only way to lower their concentration is through **dilution** ($\alpha = \alpha_{\text{dil}}$) as the cell grows. Cells grow exponentially, and by definition, the time it takes a growing cell to exactly double its volume and split into two daughter cells is called **one cell generation time** ($\tau$). 

Mathematically, the exponential growth rate of the cell's volume is locked to the generation time by the identity:
$$
\begin{equation}
\tau = \frac{\ln 2}{\alpha_{\text{dil}}}
\tag{12}
\end{equation}
$$

If we look back at our formula for response time (Equation 11) and substitute the dilution rate for a stable protein, a remarkable mathematical identity emerges:
$$
\begin{equation}
T_{1/2} = \frac{\ln 2}{\alpha_{\text{dil}}} = \tau
\tag{13}
\end{equation}
$$

**The response time of a stable protein is exactly equal to one cell generation time.** 

This simple equation carries profound biological consequences. In nature, bacteria divide every 20 to 30 minutes, while mammalian cells can take a day or longer. If a cell relies on a simple gene circuit with stable proteins to respond to a sudden environmental crisis or a toxic stressor, it will take an entire lifespan generation just to shift its internal state halfway to safety. By that time, the cell would likely perish, leaving only its daughter cells to benefit from the adaptation.

<!-- This realization transforms the mathematical response time from a simple parameter into a severe evolutionary constraint. A simple, open-loop circuit is trapped by its own growth rate. To survive in a rapidly changing world, biological networks must have evolved architectural configurations capable of breaking this one-generation speed limit.  -->

In the next chapter, we will see how the cell solves this exact engineering crisis using its very first network motif: **Negative Auto-Regulation**.

## mRNA Dynamics 

Until now, we considered the activation of transcription of a gene (mRNA production) and used a dynamical equation to describe the changes in the concentration of the gene product, the protein $Y$. In this equation, 
$$
\begin{equation}
\frac{dY}{dt} = \beta - \alpha Y,
\tag{14}
\end{equation}
$$
the parameter $\beta$ describes the rate of protein production. In reality, **mRNA needs to be translated to form the protein, and mRNA itself is also degraded by specific enzymes.**

Therefore, we start by writing the old equation for concentration of mRNA of gene $Y$, $Y_m$, as:
$$
\begin{equation}
\frac{dY_m}{dt} = \beta_m - \alpha_m Y_m,
\tag{15}
\end{equation}
$$
where mRNA is produced at rate $\beta_m$ and degraded at rate $\alpha_m$.

Now, each mRNA produces on average $p$ protein molecules per unit time, and the resulting protein is removed at rate $\alpha$. Therefore, the change in the concentration of protein $Y$ is given by:
$$
\begin{equation}
\frac{dY}{dt} = p Y_m - \alpha Y,
\tag{16}
\end{equation}
$$

The equation (16) is a coupled differential equation for $Y$ and $Y_m$ and represents a realistic model of the cell. 
# Side Quests

One of the questions that I recently started looking into is: **why does the cell always manufacture proteins?** Why not simpler molecules like sugar or fats? 

The answer that I found convincing enough is from a more engineering perspective: *Perfect Programmability*. The DNA is written in a strict, linear digital manner. Proteins are also built as linear chains by stringing together 20 different building blocks called *amino acids*. Because both are linear, the cell can translate the digital instructions of DNA directly into a physical protein chain with perfect 1-to-1 precision. You cannot do this with complex, branched molecules like fats or carbohydrates.