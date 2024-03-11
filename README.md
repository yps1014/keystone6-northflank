# keystone6-render

## setup

```
- nvm use 18
- yarn create keystone-app
    -- keystone6-render
- create a new repo at github
    -- keystone6-render
    -- git init
    -- git add *
    -- git commit -m "first commit"
    -- git branch -M main
    -- git remote add origin https://github.com/yps1014/keystone6-render.git
    -- git push -u origin main
- yarn add dotenv
    -- add import "dotenv/config" into keystone.ts and auth.ts
- touch .env
    -- create postgreSQL at render
        --- name : keystone6-render-db
        --- database : keystone6_render
        --- user : yps1014
    -- generate a random jwt secret key
        --- $ node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
- udpate keystone.ts
    -- provider: "postgresql",
    -- url: process.env.DATABASE_URL || "",
- yarn dev
- yarn build
- deploy
    -- update keystone.ts
    export default withAuth(
        config({
        ...
            graphql: {
                playground: true,
                apolloConfig: {
                    introspection: true,
                },
            },
        })
    );
    -- push source to github
```
