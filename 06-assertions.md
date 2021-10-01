---
theme: seriph
class: 'text-left'
highlighter: shiki
lineNumbers: true
---

# Un(expected)

```typescript {all|1-3|5-6|8-9|1-9|10-21|11|21|12|14-16|13|16-19|all}
await waitForExpect(async () => {
    expect(await queue.getJob(scenarioId)).toMatchObject({ data });
});

expect(response.body.data.length).toEqual(1);
expect(response.body.data[0].id).toEqual(publicProjectId);

expect(resources.length).toBeLessThanOrEqual(25);
expect(resources.length).toBeGreaterThanOrEqual(1);

it('Retrieves a JWT token ' +
    'when authenticating' +
    ' with valid credentials', async () => {
    const body = await request(app.getHttpServer())
        .post('/auth/sign-in')
        .send({
            username: E2E_CONFIG.users.basic.aa.username,
            password: E2E_CONFIG.users.basic.aa.password,
        })
        .expect(201);
    expect(response.body.accessToken).toBeDefined();
});
```

