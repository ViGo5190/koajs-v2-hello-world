Hello world for koajs@2
=======================

# Install koajs@2

```npm install koa@2 --save```

# Simple code

```
    "use strict";

    var Koa = require('koa');
    const app = new Koa();

    app.use((ctx, next) => {
        const start = new Date();
        return next().then(() => {
            const ms = new Date() - start;
            console.log(`${ctx.method} ${ctx.url} - ${ms}ms`);
        });
    });

    app.use(ctx => {
        ctx.body = 'Hello Koa@2';
    });

    app.listen(3000);
```