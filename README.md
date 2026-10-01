# Elba availability monitor

Only the public availability-check configuration is published here. The company application, founder workspace, credentials and encrypted recovery points are held separately in private storage.

A standard Ubuntu GitHub-hosted runner checks HTTPS readiness and verifies that the workspace requires authentication every ten minutes. Scheduling can be delayed by GitHub; a missed heartbeat is reported by the application. There are no AI calls, artifacts or runner caches. Standard runners in public repositories are free under [GitHub's published billing policy](https://docs.github.com/en/billing/concepts/product-billing/github-actions).

The SSH identity is stored as an Actions secret. It is restricted on the project server to a forced monitor command: no shell, forwarding, backup export or company data access. The host key is pinned. A weekly activity commit prevents the scheduler being disabled after sixty days of repository inactivity.
