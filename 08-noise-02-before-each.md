---
theme: seriph
class: 'text-left'
highlighter: shiki
lineNumbers: true
---

# No-ise - Arrange/Given

Something already happened

```typescript {2-5|8-14}
// before
const response = await request(app.getHttpServer())
    .post('/sign').send({/** */});
    
jwtToken = response.body.accessToken;

// after, within getFixtures()
return {
    cleanup: async () => {...},
    GivenUserIsLoggedIn: async () =>
        (await request(app.getHttpServer())
            .post('/sign')
            .send({})).body.accessToken,
}
```
