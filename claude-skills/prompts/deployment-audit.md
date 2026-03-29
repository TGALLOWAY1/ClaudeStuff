# Deployment Audit

Perform a comprehensive audit of the deployment pipeline and infrastructure, evaluating:

- **CI/CD Pipeline**: Build reliability, test coverage gates, deployment speed, rollback capability
- **Infrastructure**: Resource sizing, auto-scaling, redundancy, disaster recovery
- **Security**: Secret management, network policies, container scanning, access controls
- **Monitoring**: Log aggregation, alerting thresholds, uptime tracking, error rate dashboards
- **Configuration**: Environment parity, feature flags, config drift detection
- **Dependencies**: Outdated packages, vulnerability scanning, license compliance
- **Release Process**: Versioning strategy, changelog generation, canary/blue-green deployments

## Output Format

Provide findings grouped by severity (Critical, High, Medium, Low) with:
1. Pipeline stage or infrastructure component affected
2. Description of the issue
3. Recommended fix
4. Risk if left unaddressed
