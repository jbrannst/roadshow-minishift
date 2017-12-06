# roadshow-minishift

You can install roadshow guides modified to use python to run locally using minishift
1. Install minishift https://github.com/minishift/minishift
1. Install the roadshow guides https://github.com/minishift/minishift-addons/tree/master/add-ons/workshop

When minishift is running you can install the guides using these commands (taken from above docs)
```sh
git clone https://github.com/minishift/minishift-addons.git
minishift addons install minishift-addons/workshop/
minishift addon apply workshop
minishift openshift service workshop -n workshop
```
Other workshops guides and a description on how to deploy them can be found here
https://github.com/osevg/workshopper-content
Specifically to deploy the full roadshow guide
```sh
 oc new-project labs
 oc new-app osevg/workshopper -e WORKSHOPS_URLS="https://raw.githubusercontent.com/osevg/workshopper-content/master/_workshops/roadshow.yml" -e CONSOLE_ADDRESS=192.168.99.101:8443 -e ROUTER_ADDRESS=192.168.99.101.nip.io -e DOCS_URL=docs.openshift.org --name roadshow -n labs
 oc expose service roadshow --hostname roadshow.192.168.99.101.nip.io -n labs
```
