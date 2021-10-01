---
theme: seriph
class: 'text-left'
highlighter: shiki
lineNumbers: true
---

# Nest-ed Evolution

```typescript {all|2-3|7|8|9|12-21|all}
describe('OrganizationsController (e2e)', () => {
    let anOrganization: { id: string; type: 'organizations' };
    let aProject: { id: string; type: 'organizations' };

    describe('Organizations', () => {
        it('Creates an organization', async () => {
            const response = await request(app.getHttpServer()).post('/api/v1/organizations')
            anOrganization = response.body.data;
            expect(anOrganization.type).toBe('organizations');
        });
        
        it('Creates a project in the newly created organization', async () => {
            const response = await request(app.getHttpServer())
                .post('/api/v1/projects')
                .set('Authorization', `Bearer ${jwtToken}`)
                .send(createProjectDTO)
                .expect(201);

            aProject = response.body.data;
            expect(aProject.type).toBe('projects');
        });
    });
});
```
