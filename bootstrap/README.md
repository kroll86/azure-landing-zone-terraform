# bootstrap

Creates the remote backend for every other Terraform root in this repo:
a resource group, a Storage Account (Entra ID auth only, no access keys,
blob versioning + soft delete) and the `tfstate` container.

This root starts with **local state** (the backend does not exist yet),
and after the first `apply` its own state is migrated into the container
it just created (`terraform init -migrate-state`).

Status: to be written (W0).
