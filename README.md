
Modified from https://github.com/wkulhanek/docker-openshift-gitea to use a (Docker strategy) BuildConfig

When you finish the install you can add an admin use like this :

```bash
$ oc rsh $(oc get pod -l app=gitea -o name) /bin/sh -c "USER=gitea USERNAME=gitea HOME=/home/gitea GITEA_WORK_DIR=/home/gitea ./gitea admin create-user --config=/home/gitea/conf/app.ini --name god --password savethequeen --email god@olympus.com --admin"
```

(probably should do that in initContainer instead)
