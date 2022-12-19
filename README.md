# pihole-k8s

## Table of Contents
- [Pihole-on-Microk8s](#Pihole-on-Microk8s)
- [StorageClass](#StorageClass)
- [PVC](#PVC)
- [PV](#PV)
- [Service](#Service)
- [Deployment](#Deployment)

## Pihole-on-Microk8s
MicroK8s Cluster
First you should have a Kubernetes cluster up and running.  For this example, I am running microk8s on ubuntu.

All the necessary YAML files are on Github. https://github.com/jaychinut/pihole-k8s

StorageClass,PVC,PV sections are all to related to Persistent Volumes.  See official Kubernertes documentation regarding this topic.
https://kubernetes.io/docs/concepts/storage/persistent-volumes/

## StorageClass
`kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/storageclass.yaml"`

## PVC
dnsmasq persistent volume claim

`kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/claim-dnsmasq.yaml"`

etc persistent volume claim

`kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/claim-etc.yaml"`

## PV
persistent volume dnsmasq

`kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/volume-dnsmasq.yaml"`

persistent volume etc

`kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/volume-etc.yaml"`

## Service

`kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/service.yaml"`

I changed the port to 5000 and used my ubuntu host as the externalIP

## Deployment

`kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/deployment.yaml"`

I changed the WEBPASSWORD value to something else.
In this YAML file, I'm declaring the latest version of the pihole image, you can use a different tag for the version you need.
image: pihole/pihole:<TAG>