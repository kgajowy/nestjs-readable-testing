---
theme: seriph 
class: 'text-left' 
highlighter: shiki 
lineNumbers: true
---

# Every story begins with Nest

```typescript {all|1|13-15|4|5-10|all}
afterAll(async () => {/** teardown db */});

describe('OrganizationsController (e2e)', () => {
    beforeAll(async () => {
        const moduleFixture: TestingModule = await Test.createTestingModule({
            imports: [AppModule],
        }).compile();

        app = moduleFixture.createNestApplication();
        await app.init();
    });

    afterAll(async () => {
        await Promise.all([app.close()]);
    });
});
```