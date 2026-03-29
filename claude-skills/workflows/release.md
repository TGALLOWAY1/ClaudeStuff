# Release Workflow

A structured workflow for preparing and executing a release.

## Steps

1. **Pre-Release Check**: Ensure all planned changes are merged and CI is green
2. **Version Bump**: Update version numbers following semver conventions
3. **Changelog**: Generate or update the changelog with all changes since last release
4. **Testing**: Run full test suite, smoke tests, and any manual QA checks
5. **Tag & Build**: Create a git tag and trigger the release build
6. **Deploy**: Deploy to staging first, verify, then promote to production
7. **Monitor**: Watch error rates, performance metrics, and user feedback post-deploy
8. **Communicate**: Notify stakeholders and update release documentation

## Checklist

- [ ] All planned PRs are merged
- [ ] CI pipeline is green on the release branch
- [ ] Version numbers are updated
- [ ] Changelog is complete and accurate
- [ ] Staging deployment verified
- [ ] Rollback plan is documented
- [ ] Monitoring dashboards are reviewed post-deploy
