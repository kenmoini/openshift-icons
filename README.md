# openshift-icons

Custom OpenShift icons for your web console!  Largely condensed from: https://medium.com/@lbroudoux/use-custom-icons-for-your-openshift-templates-7993e5ded646

1. Get a 50x50 PNG
2. Encode to Base64
3. Add to stylesheet
4. Add stylesheet to openshift-web-console ConfigMap as cluster-admin
5. Restart the pods & clear your browser cache
6. ?????
7. PROFIT!!!!!1

**openshift-web-console ConfigMap details**

```
extensions:
  properties: {}
  scriptURLs: []
  stylesheetURLs:
    — https://your.site/linking-to/styles.css
```

**Kill the pods**
```
$ oc project openshift-web-console
$ oc delete pod `oc get pods | grep webconsole | awk '{print $1}'`
```
