# roadshow-minishift

You can install the roadshow guides locally using minishift
1. Install minishift https://github.com/minishift/minishift
1. Install the roadshow guides https://github.com/minishift/minishift-addons/tree/master/add-ons/workshop
When minishift is running you can install the guides using these commands (taken from above docs)
```sh
git clone https://github.com/minishift/minishift-addons.git
minishift addons install minishift-addons/workshop/
minishift addon apply workshop
minishift openshift service workshop -n workshop
```


