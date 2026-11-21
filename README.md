# fita-ops

Everything we use to operate Fita for customers with a maintenance contract or managed hosting.

Licensed under the Apache License 2.0, like the rest of Fita. See [LICENSE](LICENSE).

## Layout

```
console/           maintenance console (Rust + the Fita UI stack)
  server/          receives hourly health reports, keeps installation status, opens incidents
  ui/              one view with every installation and its status light
  reports/         monthly value report generation
infra/
  terraform/       one module per customer installation (VM or Kubernetes namespace, database, backups, subdomain)
  ansible/         install, upgrade and rollback playbooks
  runbooks/        what to do for each kind of incident
automation/        scripts for releases in rings and certificate renewal
docs/
  OPERATIONS.md
  ROADMAP.md
```
