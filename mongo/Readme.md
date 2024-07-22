we will populate our mongo database using the following repository

https://github.com/neelabalan/mongodb-sample-dataset

Forward the port locally and execute the script from the repo.

then. we will create a user in mongo db and use it in our application.

excecute the following inside the terminal of mongodb pod.

```bash
kubectl exec -it podname -- mongosh
```

```bash
mongosh

use admin
db.createUser({
  user: "kaizen",
  pwd: "daemon",
  roles: [
    { role: "readWriteAnyDatabase", db: "admin" },
    { role: "dbAdminAnyDatabase", db: "admin" },
    { role: "clusterAdmin", db: "admin" }
  ]
})
```
