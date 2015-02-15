---
title: The Stewart Hypothesis
layout: post
tags: ficm science notes chemistry physiology
category: ficm
published: true
---

What determines the hydrogen ion concentration (pH) in a biological system?

The traditional approach to this has used the Henderson-Hasselbach equation (pH = pKa + log ([A-]/[HA]), and the isohydric principle. The isohydric principle states that in a solution of more than one buffer, there can be only one hydrogen ion concentration which will simultaneous satisfy the dissociation of all the buffers (i.e. pKx + log(X//HX) = pKy + log(Y/HY) = . .. etc.).

Blood gas analysers measure pH and PaCO~2~ directly and from the above calculate the bicarbonate.* We then use these three values to explain whether the pH has changed due to a change in PaCO2 or a change in a non-volatile acid or base.

Stewart pointed out however that both pH and bicarbonate depend on the PaCO2 and therefore it does not make sense to try and explain a pH change in terms of the change in bicarbonate level as the two are linked. Furthermore the concentration of water in body fluids is approximately 55M (i.e. ~400x the concentration of Na+), and therefore changes in H+ ion concentrations will be buffered by the dissociation of water. He identifies instead three independent variables that predict pH: the strong ion difference, the PaCO2, and the total concentration of weak acids in the system (A-tot).

- Strong Ion Difference (SID): The difference between the sum of all the strong (or completely dissociated) cations (such as Na+, K+ etc.), and the strong anions (Cl- etc.). A strong ion is considered to be anything with a dissociation constant of <10^(4). These strong ions affect the dissociation of water. Positive strong ion differences orders of magnitude greater than the dissociation constant of water alkalinise a solution. In the extracellular fluid, sodium and chloride are the dominant strong ions and therefore simplifying SID = [Na+] - [Cl-], and this is considered an independent variable as sodium and chloride concentrations are independently regulated by the body to maintain osmolarity and cell volume.
- PaCO2 is considered an independent variable as it is independently regulated by the respiratory centre.
- A-tot is the amount of non-volatile weak acid in the solution which in the ECF is principally albumin (cf. the ICF where it is phosphate). Again, albumin concentration is independently regulated by the liver and depends on plasma oncotic pressure. @rememberthis @question

These these independent variables can be combined using simple physico-chemical laws (conservation of mass, electroneutrality, dissociation equilibrium) to create a set of simultaneous equations which can be solved for [H+].

Constituent Equations
1. Water Dissociation Equilibrium: H+ x OH- = Kw
2. Electrical Neutrality: SID + H+ = HCO3- + A- + CO3(2-) + OH-
3. Weak Acid Dissociation Equilbrium: H+ x A- = Ka x HA
4. Conservation of Mass for A: A-tot = HA + A-
5. Bicarbonate Ion formation: H+ x HCO3- = Kbc x pO2
Carbonate Ion formation: H+ x CO3(2-) = Kc x HCO3-

Stewart's Solution
a. [H+] 4 + b. [H+] 3 + c. [H+] 2 + d. [H+] + e = 0

where
* a = 1
* b = [SID] + KA
* c = {KA x ([SID] - [ATot]) - K'w - KC x pCO2}
* d = - {KA x (K'w + KC x pCO2) - K3 x KC x CO2}
* e = - (KA x K3 x KC x pCO2)

Now, because CO2 diffuses across membranes, and proteins are not able to cross membranes then the body has only one way of regulating differences in pH across membranes and that is through the SID: ie by pumping Na+/Cl- etc it can acidify urine/stomach acid