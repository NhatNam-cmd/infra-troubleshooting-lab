# infra-troubleshooting-lab
Evidence-driven network and Linux troubleshooting case studies, including incident diagnosis, root-cause analysis, fixes, and verification.

This repository documents my hands-on learning and troubleshooting practice as I prepare for Network/System/Infrastucture roles.

## Objectives
- Investigate incidents using structured hypotheses and technical evidence.
- Distinguish symptoms, observations, suspected causes, and confirmed root causes.
- Select appropriate diagnostic commands and interpret their results.
- Apply or propose minimal, safe corrective actions.
- Verify recovery at the level of original reported problem.
- Documents findings clearly for technical handoff and escalation.

## Troubleshooting Methodology

### 1. Understand the incident

- Identify the affected service, devices, users, and reported impact.
- Determine whether the issue is isolated or widespread.

### 2. From hypotheses

- List plausible causes based on the available information.
- Prioritize checks that can distinguish between competing explanations.

### 3. Collect evidence

- Inspect relevant configurations, interfaces, routes, services, and logs.
- Record observations before making changes.

### 4. Diagnose

- Compare expected behavior with observed behavior.
- Eliminate unsupported hypotheses and identify the most likely root cause.

### 5. Correct or escalate

- Apply a minimal corrective action within the permitted scope.
- Escalate when evidence, access, or authority is insufficient.

### 6. Veirfy and document

- Retest the original failure, not only an intermediate connectivity check.
- Record the outcome, remaining limitations, and relevant evidence.

## Case Studies

| ID | Case | Area | Environment | Focus |
| :--- | :--- | :--- | :--- | :--- |
| **NET-001** | [Incorrect Default Gateway](#) | Networking | Simulated incident | IPv4 gateway diagnosis, switchport checks, application verification |
| **SYS-001** | [SSH Host Key Mismatch](#) | Linux / SSH | Hands-on lab | Host identity verification and provisioning log analysis |


## Evidence Classification

Cases are labeled according to the environment and source of evidence:

- **Simulated Incident:** A guided or scenario-based exercise using provided outputs. No claim of actual device execution.

- **Hands-on Lab:** Investigation and commands executed in a personal lab environment, with recorded observations.

- **Lab Reproduction:** A recreated fault tested in a lab, with its own supporting evidence.


Case studies describe the work actually performed. Proposed commands, simulated results, and verified execution are distinguished where relevant.

## Tools and Environments

Tools are documented in the individual cases where they were used. The repository may include:

- Windows PowerShell and SSH

- Linux command-line utilities and system logs

- Network diagnostic tools and packet captures

- Cisco Packet Tracer and network device CLI

- Service health checks and configuration comparisons


## Scope

This is a learning and technical portfolio repository, not a record of production incidents. Case studies may range from foundational troubleshooting to more complex network and system investigations.

Sensitive information is excluded or sanitized before publication.