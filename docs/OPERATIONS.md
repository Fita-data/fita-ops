# Operations

## Principles

- One installation per customer. No shared processes, databases or backup keys.
- Hosted in the EU.
- Nobody accesses customer data except through emergency access that the customer approves, that expires by itself and that is recorded in their audit log.
- Secrets live in the secret manager. Never in this repository, never in Terraform state committed to git.

## Health reports

Installations with maintenance send a health report every hour if the customer enabled it. It contains version, source status, run durations, queue lengths, estimated precision, connector errors, disk space, certificate expiry and the monthly value indicators. It never contains record data or names of people. `fita health show` on the installation prints exactly what is sent.

## Incidents

The console opens an incident when a source has been failing for hours, a queue is stuck, precision drops or a certificate is about to expire. The incident goes to the support channel with context attached. On hosted installations we act directly. On customer installations the console prepares the change and the customer approves it.

## Upgrades

Rings. Internal installation first, then a small group of customers, then the rest, always inside the window agreed with each customer. Every upgrade has a tested rollback.

## Backups

Continuous, point in time recovery for the last 30 days. Restore is tested monthly on a random installation.

## Hosted installations and the agent

When the sources are inside the customer network, the `agent` role runs there and opens an outbound mutual TLS connection to the hosted installation. Source credentials stay with the agent.

## Monthly value report

Generated per customer from the health reports. Duplicates prevented at creation, records unified, issues solved and their impact, precision, source status and the work we did that month.
