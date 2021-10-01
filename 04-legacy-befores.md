---
theme: seriph
class: 'text-left'
highlighter: shiki
lineNumbers: true
---

# Setup hell

```typescript {all|7-9|11-13|16|all}
describe('OrganizationsController (e2e)', () => {
    let app: INestApplication;
    let jwtToken: string;

    beforeAll(async () => {
        app = ...;
        const response = await request(app.getHttpServer())
            .post('/auth/sign-in').send({}).expect(201);
        jwtToken = response.body.accessToken;
    });
    
    beforeEach(async () => {
        // stubs, mocks, spies...
    })
    
    it('should ...', () => {...})
});
```
