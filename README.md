# Google-Cloud-Networking
Google Cloud Networking


Day one of the Google Cloud Professional Certification Journey


Gloud commands
gcloud compute networks create managementnet --project=qwiklabs-gcp-03-3a49b250b163 --subnet-mode=custom --mtu=1460 --bgp-routing-mode=regional && gcloud compute networks subnets create managementsubnet-us --project=qwiklabs-gcp-03-3a49b250b163 --range=10.130.0.0/20 --stack-type=IPV4_ONLY --network=managementnet --region=us-east4 && gcloud compute firewall-rules create managementnet-allow-custom --project=qwiklabs-gcp-03-3a49b250b163 --network=projects/qwiklabs-gcp-03-3a49b250b163/global/networks/managementnet --description=Allows\ connection\ from\ any\ source\ to\ any\ instance\ on\ the\ network\ using\ custom\ protocols. --direction=INGRESS --priority=65534 --source-ranges=10.130.0.0/20 --action=ALLOW --rules=all && gcloud compute firewall-rules create managementnet-allow-icmp --project=qwiklabs-gcp-03-3a49b250b163 --network=projects/qwiklabs-gcp-03-3a49b250b163/global/networks/managementnet --description=Allows\ ICMP\ connections\ from\ any\ source\ to\ any\ instance\ on\ the\ network. --direction=INGRESS --priority=65534 --source-ranges=0.0.0.0/0 --action=ALLOW --rules=icmp && gcloud compute firewall-rules create managementnet-allow-rdp --project=qwiklabs-gcp-03-3a49b250b163 --network=projects/qwiklabs-gcp-03-3a49b250b163/global/networks/managementnet --description=Allows\ RDP\ connections\ from\ any\ source\ to\ any\ instance\ on\ the\ network\ using\ port\ 3389. --direction=INGRESS --priority=65534 --source-ranges=0.0.0.0/0 --action=ALLOW --rules=tcp:3389 && gcloud compute firewall-rules create managementnet-allow-ssh --project=qwiklabs-gcp-03-3a49b250b163 --network=projects/qwiklabs-gcp-03-3a49b250b163/global/networks/managementnet --description=Allows\ TCP\ connections\ from\ any\ source\ to\ any\ instance\ on\ the\ network\ using\ port\ 22. --direction=INGRESS --priority=65534 --source-ranges=0.0.0.0/0 --action=ALLOW --rules=tcp:22


**Command to create a network called privatenet**
- gcloud compute networks create privatenet --subnet-mode=custom

**Create subnet create the privatesubnet-us**
gcloud compute networks subnets create privatesubnet-us --network=privatenet --region=us-east4 --range=172.16.0.0/24

![image](https://github.com/Hillykyp/Google-Cloud-Networking/assets/47059631/b3674131-7be1-45aa-b151-9c75da5892cf)


