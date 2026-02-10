# Troubleshooting & Support Guide: Databricks Job Monitoring Agent

## Common Issues & Resolutions

### 1. Databricks API Authentication Errors
- **Symptom:** Agent fails to connect or returns authentication errors.
- **Resolution:**
  - Verify `DATABRICKS_TOKEN` validity and permissions.
  - Ensure `DATABRICKS_INSTANCE` URL is correct.
  - Confirm network access to Databricks workspace.

### 2. GitHub Upload Failures
- **Symptom:** CSV or documentation files not appearing in GitHub directory.
- **Resolution:**
  - Check `GITHUB_TOKEN` validity and repo write access.
  - Ensure correct `repo`, `branch`, and `folder_name` configuration.
  - Review agent logs for API error details.

### 3. CSV Formatting Problems
- **Symptom:** CSV files are malformed or missing fields.
- **Resolution:**
  - Confirm agent version matches expected CSV schema.
  - Validate job names and error extraction logic in config.
  - Manually inspect CSV output for delimiter or encoding issues.

### 4. Missing or Incomplete Error Reports
- **Symptom:** Expected job failures not reported.
- **Resolution:**
  - Ensure `JOB_NAMES` in config match actual Databricks job names.
  - Check for recent job runs in Databricks UI.
  - Review agent logs for skipped jobs or silent errors.

## Diagnostic Procedures
1. Review agent execution logs for stack traces or error codes.
2. Manually test Databricks and GitHub API connectivity using curl or Postman.
3. Cross-check configuration files for typos or missing values.
4. Re-run the agent with debug logging enabled for detailed output.

## Support & Escalation
- For unresolved issues, contact the Data Engineering or DevOps support team.
- Provide agent logs, configuration files, and error messages when escalating.
- For urgent issues (e.g., recurring job failures, compliance deadlines), escalate to team leads or platform owners.

## Additional Resources
- [Databricks API Docs](https://docs.databricks.com/api/)
- [GitHub REST API Docs](https://docs.github.com/en/rest)
- Internal runbook: See `setup_and_usage.md` in this directory.
