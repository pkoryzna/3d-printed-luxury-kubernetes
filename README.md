# 3d-printed-luxury-kubernetes
k8s maximalism yay

## install
MAKE SURE THE PRINTER AND WEBCAM ARE CONNECTED AND ON - otherwise your pods will keep waiting for device files to show up.

```
cp example_values.yaml values.yaml
```

and customize the device names, domains and paths to taste.


Then

```
helm upgrade --namespace 3dprinting --install release_name .
```

For first time install only, you'll need to label the k8s node to enable smarter-device manager:

```
kubectl label nodes/$NODE_NAME smarter-device-manager=enabled
```

After that, go on and configure octoprint through web UI once everything starts.

happy 3d printing!