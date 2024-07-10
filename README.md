# 3d-printed-luxury-kubernetes

Kubernetes Maximalism Meets Molten Plastics.

This Helm chart will install an instance of OctoPrint in a StatefulSet, 
`smarter-device-manager` to pass the serial device (and webcam),
and if a webcam is configured, `motion` webcam server to provide the MJPEG stream to OctoPrint.

I have been using this chart for over a year at home, and the only time I had to redo this setup
was when I hosed the k3s node 🙄 (skill issue)

## install

Before starting - MAKE SURE THE PRINTER AND WEBCAM ARE CONNECTED, AND POWERED ON! 
Otherwise your pods will keep waiting for device files to show up.

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
