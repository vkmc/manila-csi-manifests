
00-writer-pod.yaml and 11-writer-pod.yaml both use the same PVC so they
both mount the same persistent volume at /mnt/test and their busybox
container writes the date every few seconds to /mnt/test/$hostname.

These pod manifests are identical except for their hostnames but because
their hostnames differ the deployed containers will write to distinct
files under /mnt/test.

