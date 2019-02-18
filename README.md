# Reveal.js template slides

This repository contains a template for reveal.js presentation slide.

1. Fork this repository
2. Setup CI/CD (project name in `.gitlab-ci` file, Openshift config)
3. Edit `index.html`
4. Edit main title, Authors in README.md

To Redirect HTTP Traffic to HTTPS, edit your route via `oc edit route` and add `insecureEdgeTerminationPolicy: Redirect`.

```
apiVersion: v1
kind: Route
metadata:
  name: route-edge-secured-redirect-insecure 
spec:
  host: www.example.com
  to:
    kind: Service
    name: service-name 
  tls:
    termination:                   edge      
    insecureEdgeTerminationPolicy: Redirect  
    [ ... ]
```


### Usage

Open index.html in your browser or deploy this on OpenShift e.g. (see `.gitlab.yml`)

* presentation mode: press `s`
* overview mode: press `escape`
* pdf/print version: go to http://your_slides_url/?print-pdf#/

See OpenShift usage documentation for deployment instructions: https://git.cetic.be/OpenShift/documentation/tree/master/webconsole/#tldr

Result is here: http://presentation-template.openshift.ext.cetic.be

### References

* https://github.com/hakimel/reveal.js/

### Authors

* **Alexandre Nuttinck** : alexandre.nuttinck@cetic.be
* **Sebastien Dupont** : sebastien.dupont@cetic.be
