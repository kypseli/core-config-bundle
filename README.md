# core-config-bundle
CloudBees Core Config Bundle examples for preview/demo environments

## Manage Bundles

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
