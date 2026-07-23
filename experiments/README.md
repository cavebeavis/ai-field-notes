# Experiments

This directory contains code, fixtures, datasets, prompts, measurements, and demonstrations used to test claims about AI systems.

Each experiment should live in its own subdirectory and include a README based on [`../templates/experiment.md`](../templates/experiment.md).

An experiment must record enough context to explain what actually happened, including model and provider versions where available, parameters, tool access, date, inputs, method, raw observations, and limitations. AI behavior drifts; an unexplained result is not durable evidence.

Do not commit credentials, proprietary repositories, private prompts, customer data, employer-confidential material, or copyrighted datasets that cannot be redistributed.

Generated code should remain only when it supports reproducibility or becomes a useful retained capability. Delete unexplained one-off output rather than turning this directory into a dump.
