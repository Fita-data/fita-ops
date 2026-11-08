# fita-ops

> Private repository. Do not copy its contents to public repositories, issues or docs.

Everything we use to operate Fita for customers with a maintenance contract or managed hosting.

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
