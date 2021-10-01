---
theme: seriph
class: 'text-left'
highlighter: shiki
lineNumbers: true
---

# No-ise - setup chore

```typescript {all|1|2|4|5|7-12|all}
const getFixtures = async () => {
    const app = await bootstrapApplication(); // or module
    
    const sut = app.get(SubjectUnderTestClass);
    const cleanups: (() => Promise<void>)[] = []
    
    return {
        cleanup: async () => {
            await Promise.all(cleanups);
            await app.close();
        }
    }
}
```

