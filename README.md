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

## StorageClass
kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/storageclass.yaml"

## PVC
dnsmasq persistent volume claim

kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/claim-dnsmasq.yaml"

etc persistent volume claim

kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/claim-etc.yaml"

## PV
persistent volume dnsmasq

kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/volume-dnsmasq.yaml"

persistent volume etc

kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/volume-etc.yaml"

## Service

kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/service.yaml"
I changed the port to 5000 and used my ubuntu host as the externalIP

## Deployment

kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/deployment.yaml"
<<<<<<< HEAD
I changed the WEBPASSWORD value to something else.
=======
I changed the WEBPASSWORD value to something else. This deployment has 1 replica as it doesn't need to scale for my use case.
>>>>>>> 87a1f5c (modified README.md)
