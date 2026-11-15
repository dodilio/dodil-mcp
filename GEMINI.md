# Working with Dodil

Dodil is a cloud platform: one data system (K3) that serves SQL, vector, graph
and S3 objects over the same rows, Dodil Git with CI, Ignite app hosting, and
AppID sign-in for the apps you build. The `dodil` MCP server in this extension
exposes it as tools named after the CLI command path, such as
`data_bucket_list`, `git_repo_create` or `ignite_app_get`.

## Getting oriented

- The server's resources hold the guides: `dodil://build` for building an app
  or business system end to end, `dodil://recipes` for common multi-step
  tasks, and `dodil://k3/sql` for the data model. Reading the relevant one
  first is faster than discovering the steps tool by tool.
- Each tool's input schema lists its required parameters; most data tools
  need a `bucket`.
- `auth_orgs` lists the organizations this connection can act in. With more
  than one, pass `org` on each call.

## Sign-in

The first tool call opens Dodil's sign-in page in the browser
(connect.dodil.io). The user picks which organizations to grant. To change
that later, they reconnect, or revoke the connection under Connected apps in
the Dodil console.

## Care with writes

Tools carry read-only and destructive hints. Confirm with the user before a
destructive call (deletes, SQL that changes data, deploys, visibility changes,
anything that sends email or moves money), and say which organization it
acts in.
