# core-config-bundle
CloudBees Core Config Bundle examples for preview/demo environments

## Manage Bundles
Every Core Master (Managed Master (MM)) must have its own bundle directory and files stored in the Operations Center (OC) `jcasc-bundles-store` directory.

### Base bundle
The base bundle will be used to create the initial individual, branch and MM specific bundles by merging it with the MM bundle at copy time. 

### Branch per bundle
Each unique MM bundle will be represented by its own branch that matched the MM name and the Jenkins Pipeline job will use the branch name to determine what directory name to copy to the `jcasc-bundles-store` directory on OC.

### Copy bundle to Operations Center:

```bash
kubectl cp --namespace core test-2-190-3-2-1 cjoc-0:/var/jenkins_home/jcasc-bundles-store/
```

### List Bundles on Operations Center:

```bash
kubectl exec --namespace core cjoc-0 -- \
ls /var/jenkins_home/jcasc-bundles-store | grep -v security.xml
```


kubectl cp --namespace core \
cjoc-0:/var/jenkins_home/jcasc-bundles-store/security.xml security.xml


kubectl cp --namespace core security.xml \
cjoc-0:/var/jenkins_home/jcasc-bundles-store/security.xml
