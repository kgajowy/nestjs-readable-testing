---
theme: seriph
class: 'text-left'
highlighter: shiki
lineNumbers: true
---

# No-ise - Arrange/Given

Dependency setup

```typescript {1-4|14-19|7-10}
fakeQueue.getJob.mockImplementation(async (id) => {
        expect(id).toBe('123');
        return {id: '123'} as Job;
    });

// fixtures
fakeQueue
    .getJob
    .mockImplementation(async () => 
        throw new Error(`Unexpected call`))

return {
    cleanup: async () => {...},
    GivenAHeavyComputationRequestWasSubmitted() => {
        fakeQueue.getJob.mockImplementation(async (id) => {
            expect(id).toBe('123');
            return {id: '123'} as Job;
        });
    }
}
```
