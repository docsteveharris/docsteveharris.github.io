---
title: Simpson's Paradox backwards
category: blog
tags: [statistics, tutorial]
published: True
excerpt: 
image: 
  feature:
comments: true

---

I have been enjoying reading Judea Pearl's new book _Causal Inference in Statistics: A primer_[^1]

Following on from their example, consider trying to choose between two doctors. You automatically choose the one with the best outcomes. But suppose the one with the best outcomes chooses the easiest cases. The other's poorer record is a consequence of trickier work. Now who do you choose? Better to look at the results stratified by difficulty and then decide.

There is another side to the coin however which says that the stratified outcomes would lead you to the wrong choice. This time consider choosing to use a drug or not. The drug has a toxic side effect, but its therapeutic mechanism of action is through lowering blood pressure. Overall, the drug improves outcomes in the population, but when stratifying on _post-treatment_ blood pressure the outcomes are worse in both the low and the high blood pressure groups. How can this be true? Because we have unintentionally stratified on the outcome, and within each outcome all that remains to observe is the toxic side effect.

To clarify, imagine the drug is designed to fix broken hearts, and it does this by lowering the blood pressure, and instead of stratifying on blood pressure we stratify on fixed hearts. When the drug works, the heart is fixed (and the blood pressure will be lower), but some of the patients will also get the toxic side effect. Because the drug works, the 'fixed heart' group will have more patients who have taken the drug, than there are patients taking the drug in the 'broken' heart group. More patients taking the drug means more patients getting side effects, and apparently (but falsely) better outcomes for patients who didn't take the drug.

The patients who get better without taking the drug are just lucky. The patients who took the drug and got better are a mixture of those who needed the drug to get better, and those who would have been lucky anyway. Examining only patients with 'fixed hearts' means excluding patients who _would have_ been fixed had they taken the drug. Excluding such patients means excluding the harm from _not taking_ the drug which in turn means we only see the harm from _taking_ the drug. 

Simpson's paradox arises when there is a cause  for the outcome other than the treatment such as the fact that your doctor only does tricky cases. Controlling for the common cause (tricky versus easy cases) allows us to see the true effect. In the latter example, we have unintentionally stratified on an outcome not on a cause which means the true answer is in the aggregate not the stratified data.

[^1]: Pearl J. Causal Inference in Statistics. John Wiley & Sons; 2016