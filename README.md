This work is leveraging the work from other repositories such as:

* https://github.com/jboss-openshift/cct_module
* https://github.com/jboss-container-images/jboss-webserver-5-openshift-image

## Add required files

```shell
MAVEN_REPO=https://maven.repository.redhat.com/ga

for artifact in $(cat artifacts.txt)
do
  cekit-cache add $MAVEN_REPO/$artifact --md5 $(curl $MAVEN_REPO/$artifact.md5)
done
```

Download your jws artifacts and add them to the jws-unpack-tomcat9 module: [](tomcat-ubi8/modules/jws-unpack-tomcat9/x86_64/module.yaml).
Be sure to include the md5 for each added component.