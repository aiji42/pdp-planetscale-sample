```bash
yarn install
touch .env # set DATABASE_URL={your planetscale endpoint}?sslaccept=accept_invalid_certs

docker-compose up
```

```bash
yarn prisma db push
yarn prisma generate --data-proxy
NODE_TLS_REJECT_UNAUTHORIZED=0 DATABASE_URL=prisma://localhost?api_key=foobar node
```

On node console
```node
const { PrismaClient } = require('@prisma/client')
const prisma = new PrismaClient()
await prisma.user.findMany()

// > []
```