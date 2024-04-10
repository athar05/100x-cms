<h1 align='center'>CMS</h1>

## Setup Procedure

* Docker

    OR

* Copy .env.example to .env
* Get a postgres db from https://neon.tech/ (or any other provider)
* Replace the DATABASE_URL in .env
* Run ```npx prisma migrate dev``` to setup schema
## Steps to run locally
With Docker

* ```docker compose up```

**Note:** 

* You might encounter `Error response from daemon: Ports are not available: exposing port TCP 0.0.0.0:5432 -> 0.0.0.0:0: listen tcp 0.0.0.0:5432: bind: address already in use` when you run  ```docker compose up```. 
* This means that there is already a proccess running on port 5432, typically a PostgreSQL service. Follow the below steps to resolve the issue: 
- Get the pid of the proccess that is running on port 5432: ```sudo lsof -i :5432```
- Terminate all the processes that are running on this port: ```sudo kill -9 <pid>```
- Run the command again to verify no process is running now: ```sudo lsof -i :5432```
- Run ```docker compose up``` again


Without Docker
* ```npm install```
* ```npm run db:seed``` to seed the database
* ```npm run dev```
* Login using any userid and password 123456
* You should be able to see some test courses

---

Read [contributing guidelines](./CONTRIBUTING.md) to start making contributions
