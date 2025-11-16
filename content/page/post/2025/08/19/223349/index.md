{"author":"ip-note","title":"US Patent Law - Section 101 (Subject Matter Eligibility)","draft":"false","date":"2025-08-19","image":"20250524112124.png","categories":["特許権","知的財産権全般"]}
In U.S. patent applications, many people struggle with § 101 rejection.

Of course I’m one of them.

As a personal memorandum, I’d like to leave some countermeasures to avoid § 101 rejection.

This is merely my personal opinion and should be taken as such.

<h3 id="Decision-Flow">Decision Flow</h3>

First, the following is the basic flow for determining patent eligibility.

<div class="images-row mceNonEditable">
{{< figure src="image/20250524112124.png" >}}
</div>

<div style="text-align: center;">MPEP §2106</div>

<h3 id="Step-1">Step 1</h3>

If the claim falls within one of the statutory categories (process, machine, manufacture, or composition of matter), then it clears the first hurdle and proceeds to Step 2A.

If not, it is deemed “ineligible subject matter” and the examination ends immediately.

In Japan, program claims are accepted, but in U.S. applications, they need to be amended into something like computer-readable medium claims.

<h3 id="Step-2A">Step 2A</h3>

In Step 2A, as shown on the right, patent eligibility is judged under the following two prongs.

<h4 id="Prong-1">Prong 1</h4>

It is determined whether the claim recites one of the judicial exceptions.

If not, it is considered “eligible.” If it does, then the analysis proceeds to Prong 2.

- Abstract ideas
    - Mathematical concepts
    - Methods of organizing human activity
    - Mental processes
- Laws of nature
- Natural phenomena

<h4 id="Prong-2">Prong 2</h4>

Even if a claim involves one of the above judicial exceptions, it is considered “eligible” if <strong>additional elements integrate the exception into a practical application</strong>.

If eligibility is still not recognized under Prong 2, the analysis moves on to Step 2B.

<h3 id="Step-2B">Step 2B</h3>

If the claim provides an “inventive concept”, it is deemed “eligible.”

If it does not, then it is “ineligible,” and the examination ends.

The presence of an “inventive concept” is evaluated based on whether the claim shows a technically meaningful improvement or practical utility beyond the judicial exception (for example, enhancing the functions of a particular technical field or solving a specific technical problem).

From my practical experience, most of the battle against § 101 rejection happens within Step 2A (Prongs 1 and 2).

At least in my surroundings, I’ve never seen a case where eligibility was recognized under Step 2B. If a claim isn’t deemed eligible under Prong 2, the chances of succeeding in the more difficult Step 2B (at least in my view) are extremely low.

Frankly, the Step 2B standard feels like it’s judged on novelty or non-obviousness factors, so it doesn’t quite make sense to me why it should be tied to patent eligibility.

There is, however, one hypothetical case example provided by the USPTO.

So, how should we argue patent eligibility?

<h3 id="Strategy">Strategy</h3>

In Step 2A, Prong 1, abstract ideas are the major barrier—especially “mental processes,” which are particularly tricky.

If something can be carried out entirely in the human mind, it tends to be categorized as a mental process.

For example, in a hypothetical GUI case published by the USPTO, determining the frequency of icon usage over a given time period was considered, in its broadest form, to be a mental process.

<h4 id="Referring-to-internal-processing">Referring to internal processing?</h4>

On the other hand, if the claim specifies that a processor tracks the amount of memory allocated to each application linked with an icon, and determines icon usage over a period of time, then it is judged not to be a mental process, because it involves processor operations that cannot be performed solely in the human mind.

However, such descriptions require reference to the internal operations of a device or program, <strong>which greatly undermines the detectability of infringement</strong>.

Of course, if the inventive point lies in the internal processing itself, then it’s fine (setting aside the argument of whether it should be kept as a secret know-how instead of disclosed). But otherwise, I personally prefer not to draft claims this way.

So in reality, I believe the practical approach is to aim for Prong 2.

<h4 id="Aiming-for-eligibility-under-Prong-2">Aiming for eligibility under Prong 2</h4>

In the GUI hypothetical case, even though the step of determining icon usage was a mental process, the USPTO considered the claim eligible because it further included automatically moving the most frequently used icon to the position closest to the start icon on the GUI (an additional element beyond the mental process), thereby providing a specific improvement over prior systems.

In other words, even if a claim refers to an abstract idea, it can still be made eligible by <strong>claiming the actual output operation performed by the device—using the information derived from the idea in a way that leads to improvements in a specific technical problem</strong>.

But not just any output will suffice—the output must realistically direct to an improvement in computer functionality or in a particular technical field.

Simply stating “outputting the result” is merely executing a general computer function, and is no different from an instruction to apply an abstract idea. So it’s important to mention more specific characteristics of the output.

In one real case I handled, simply adding the element of “displaying a warning” based on the obtained determination result was enough to overcome the § 101 rejection.

Presumably, it was recognized that the warning display allowed users to quickly and easily identify situations where problems might arise in a certain technical field.

Of course, adding a warning display element does not guarantee to avoid § 101 rejection.

<h3 id="Conclusion">Conclusion</h3>

Thus, when drafting specifications, it is helpful to include not only steps for information processing but also:

- Implementation examples where the obtained information is used to produce some kind of output
- A description of how that output improves a technical problem

By doing so, you may be able to avoid § 101 rejections while still preserving claim value.