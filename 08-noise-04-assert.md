---
theme: seriph
class: 'text-left'
highlighter: shiki
lineNumbers: true
---

# No-ise - Asset/Then (it, test)

Mysteries explained

```typescript {1-2|8-11|4-5|12-17}
expect(response.body.data.length).toEqual(1);
expect(response.body.data[0].id).toEqual(publicProjectId);

expect(resources.length).toBeLessThanOrEqual(25);
expect(resources.length).toBeGreaterThanOrEqual(1);

return {
    ThenResponseContainsTheOnlyPublicProject: (response: supertest.Response) => {
        expect(response.body.data.length).toEqual(1);
        expect(response.body.data[0].id).toEqual(publicProjectId);
    },
    ThenResponseHasPagination: (response: supertest.Response) => {
        expect(response.body.metadata.pagination).toEqual({
            pages: 1,
            limit: 25, // different? yes, developer meant to check pagination!
        })
    }
}
```

