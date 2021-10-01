---
theme: seriph
class: 'text-left' 
highlighter: shiki 
lineNumbers: true
---

# No-ise - Asset/Given (beforeEach)
```typescript
const response = await request(app.getHttpServer())
    .post('/auth/sign-in').send({}).expect(201);
jwtToken = response.body.accessToken;
```

```typescript
return {
    cleanup: async () => {...},
    GivenUserIsLoggedIn: async () =>
        (await request(app.getHttpServer())
            .post('/auth/sign-in')
            .send({})).body.accessToken,
}
```


// TODO 
pokaz inne opcje

GivenAJobInQueue() {
fakeQueue.getJob.mockImplementation(async (id) => {
expect(id).toBe('123');
return { id: '123' } as Job;
});
},





4:53
GivenAssetsAvailable() {
fakeAssets.forScenario.mockImplementation((id) => {
expect(id).toBe(`scenario-1`);
return this.scenarioAssets;
});
},