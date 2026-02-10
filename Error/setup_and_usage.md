# Databricks Job Error Monitoring Agent - Setup & Usage Guide

## Overview
This guide describes how to configure, deploy, and operate the automated Databricks job error monitoring and reporting agent. The agent monitors specified Databricks jobs, detects failures, generates structured CSV error reports, and uploads them to a designated GitHub directory for audit and collaboration.

## Prerequisites
- Databricks workspace URL and API token with read access to jobs and runs
- GitHub repository and Personal Access Token (PAT) with repo write permissions
- Python 3.8+ environment (for agent execution)
- Outbound network access to Databricks and GitHub APIs

## Setup Instructions
1. Clone this repository and navigate to the agent directory.
2. Configure environment variables or a secure config file with:
    - `DATABRICKS_INSTANCE` (e.g., `https://dbc-xxxx.cloud.databricks.com`)
    - `DATABRICKS_TOKEN` (Databricks API token)
    - `GITHUB_TOKEN` (GitHub PAT)
    - `JOB_NAMES` (comma-separated list of Databricks job names to monitor)
    - `GITHUB_REPO` (e.g., `Tanmay-analyst/Databricks_Pipeline_monitor`)
    - `GITHUB_BRANCH` (e.g., `main`)
    - `GITHUB_FOLDER` (e.g., `Error`)
3. Run the agent script manually or schedule via cron/CI/CD for periodic execution.

## Configuration Steps
- Customize the monitoring interval (e.g., hourly, daily) as needed.
- Adjust CSV schema or output directory via agent settings.
- Add/remove job names in the configuration file as pipelines evolve.

## Usage Guidelines
- On each run, the agent will:
    1. Connect to Databricks and enumerate jobs.
    2. Detect and extract error/failure events.
    3. Generate a structured CSV error report.
    4. Upload the CSV to the configured GitHub folder.
- Review error reports in GitHub for actionable insights and compliance/audit needs.

## Maintenance Procedures
- Rotate API tokens regularly and update configuration as needed.
- Periodically review agent logs for unexpected failures.
- Update job lists and reporting logic as new jobs are added or requirements change.
- For major Databricks/GitHub API changes, update the agent accordingly.

## Support
- For troubleshooting, see `troubleshooting.md` in this directory.
- For escalation, contact the DevOps or Data Engineering team leads.
