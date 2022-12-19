# pihole-k8s
#Pihole on MicroK8s Kubernetes
#MicroK8s Cluster
#First you should have a Kubernetes cluster up and running.  For this example, I am running microk8s on ubuntu.

#All the necessary YAML files are on Github. https://github.com/jaychinut/pihole-k8s

#Storage Class#
kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/storageclass.yaml"

#Persistent Volume Claims

#dnsmasq persistent volume claim
kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/claim-dnsmasq.yaml"

#etc persistent volume claim
kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/claim-etc.yaml"

#Persistent Volumes

#volume dnsmasq
kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/volume-dnsmasq.yaml

#volume etc
kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/volume-etc.yaml"

#Service
kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/service.yaml"
#I changed the port to 5000 and used my ubuntu host as the externalIP

#Deployment
kubectl apply -f "https://github.com/jaychinut/pihole-k8s/blob/main/deployment.yaml"
#I changed the WEBPASSWORD value to something else.
