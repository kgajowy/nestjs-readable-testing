---
theme: seriph
class: 'text-left'
highlighter: shiki
lineNumbers: true
---


# No-ise - Act/When (beforeEach)

```typescript {1-10|2-6|13-17}
it('Creates a project in the newly created organization', async () => {
    const response = await request(app.getHttpServer())
        .post('/api/v1/projects')
        .set('Authorization', `Bearer ${jwtToken}`)
        .send(createProjectDTO)
        .expect(201);

    aProject = response.body.data;
    expect(aProject.type).toBe('projects');
});

{
    WhenCreatingAProjectWithName: async (name: string) => (await request(app.getHttpServer())
        .post('/api/v1/projects')
        .set('Authorization', `Bearer ${jwtToken}`)
        .send({name})
        .expect(201)).body

}

```

