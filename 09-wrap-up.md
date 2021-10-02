---
theme: seriph
class: 'text-left'
highlighter: shiki
lineNumbers: true
---

# Putting pieces together

```typescript {1-4|7|8|9|10|11|15|16|17|18|all}
let fixtures: FixtureType
beforeEach(async () => {
    fixtures = getFixtures();
})

// e2e/integration example
test(`User can create project within his organization`, async () => {
    await fixtures.GivenUserIsLoggedIn();
    const organizationId = await fixtures.GivenOrganizationWasCreated();
    const projectId = await fixtures.WhenCreatingAProject(organizationId);
    await fixtures.ThenProjectIsListedInCatalogue(projectId);
})

// unit/integration example
test(`completing computation job triggers SomeIntention`, async () => {
    const requestId = await fixtures.GivenAHeavyComputationRequestWasSubmitted();
    await fixtures.WhenJobIsCompleted(requestId);
    await fixtures.ThenSomeIntentionIsOnCommandBus();
})


```

