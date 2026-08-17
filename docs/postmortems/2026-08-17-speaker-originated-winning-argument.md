# The Speaker originated its own winning argument

- **Date:** 2026-08-17
- **Severity:** High. The verdict rested entirely on an unchecked claim.
- **Found by:** The Comptroller, which then partly falsified the argument using the Speaker's own document
- **Status:** Fixed, see [ADR-0007](../adr/0007-speaker-may-reason-but-not-win-alone.md)

## What happened

By the final stage of run 2, every instrument had failed. The polling had been discredited by one department, and another had ruled the behavioural data irrelevant to the question as framed.

The Speaker invented an argument to fill the gap, wrote it as a finding, and won the verdict on it. No department had produced it. No researcher had gathered evidence for it. No auditor had seen it.

The Comptroller then went and checked it, and found the claim false as stated.

## Impact

Contained. The Comptroller caught it before the verdict reached the user, and the falsification appears in the published report directly beneath the ruling it undermines.

Had the Comptroller not existed, the run would have produced a confident, well-structured, entirely unchecked answer.

## Root cause

The Speaker is the only body in the design with nothing above it. Every other agent's output is read by something whose job is to check it. The Speaker's output went straight to the user.

Compounding it: nothing in the design distinguished "the Speaker recombined what departments found" from "the Speaker made this up", so the two arrived in the same voice.

## Fix

Originating an argument stays allowed, because a Speaker confined to recombination returns nothing when every instrument has failed. Two conditions added:

1. Anything not traceable to a department goes in a named section, "What I reasoned myself".
2. It may not be the sole basis of the ruling. If it is, the honest verdict is that the question cannot be settled on the evidence gathered.

The Comptroller now has a standing duty to test whatever gets declared, and to rule on the confidence it was stated at, not only its content.

## Did the fix work

Partly, and informatively. On the next run the Speaker declared "none: every element traces to an agent's finding". The Comptroller checked and found three undeclared originations, including a decision threshold that appeared nowhere in the record.

So the rule did not stop origination. It gave the checking layer something specific to check against, which is what caught it.
