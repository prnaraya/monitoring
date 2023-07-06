# KubevirtHyperconvergedClusterOperatorSingleStackIPv6
<!-- Edited by dharmit, Jul 2023-->

## Meaning

This alert fires when user tries to install OpenShift Virtualization on a single stack IPv6 cluster.

OpenShift Virtualization is not supported on an OpenShift cluster configured with single stack IPv6.

## Impact

OpenShift Virtualization Operator can't be installed on a single stack IPv6 cluster, and hence creation virtual 
machines atop such a cluster is not possible.

## Diagnosis

Check the `Status` field in the output of `kubectl describe network cluster`. It contains only an IPv6 CIDR under 
`Cluster Network`.

## Mitigation

It is recommended to use single stack IPv4 or a dual stack IPv4/IPv6 networking to use OpenShift Virtualization. 
Refer the [documentation](https://docs.openshift.com/container-platform/latest/networking/ovn_kubernetes_network_provider/converting-to-dual-stack.html).