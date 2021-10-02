---
theme: seriph
class: 'text-left'
highlighter: shiki
lineNumbers: true
---

# Clean'em up 🕸️

```typescript {all|3-8|10-14|all}
{
    GivenSomething: async () => {
        const ids = await repo.insert([/** */]);
        cleanups.push(() => repo.delete({
            where: {
                id: In(ids), // "compensate"
            }
        }))
    }
    cleanup: async () => {
        // previously pushed clean functions
        await Promise.all(cleanups.map(clean => clean()));
        await app.close();
    }
}

```

