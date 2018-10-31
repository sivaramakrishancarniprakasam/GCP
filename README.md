# GCP

## GCP Design

### Introduction

- **GCP**: Compute + Storage + Networking + BigData + Machine Learning
- **Cloud Computing**: On-Demand + Broad Network Access + Resource Pooling + Elasticity + Measured Services (_Pay per use_)
- **History `<->` Future**: On Perm `->` Virtual `->` Serverless
- **Compute**: (Managed Infra) `<-` Compute Engine (_IaaS_) `-` Kubernetes Engine (_Hybrid_) `-` App Engine (_PaaS_) `-` Cloud Functions (_Serverless_) `-` Managed Services (_Automated Elastic Resource_) `->` (Dynamic Infra)
- Environmental Concerns - 0 Carbon Emission and 100% Renewable Energy
- Encryption at Rest, In Transition, DDoS, Google Frontend Test for Vulnerablilities
- Built on **OpenAPIs** like kubernetes, Hadoop, Apache HBase which are opensource

### Physical Infrastructure

Global System (_Internet_) `->` Points of Presence (_Edge Locations and CDNs_)
`->` Global (_Private Global Network_)
`->` Multi Region
`->` Region (_Each region separated by 160KM/100Miles_)
`->` Zones (_Think of them as separate facilities_)
`->` Datacenters
`->` Rack
`->` Physical Server
`->` vCPU (**2vCPU = 1 core**)

### Cloud Platform Hierarchy

- Organization Nodes `->` Folders (_It is must to have org node to create folders_) `->` Projects `->` GCP Resources
  - Policies are inherited from top (eg. Org node), with more generous of them taking precedence (_consider it binary OR of access level_)
  - Org node can be create by using Cloud Identity
  - Billing is per project basis
- Compute Resources, IAM, least privilige, raw compute to managed services, access using web console/cli-tools/iOS/Android/APIs
- Resources are allocated based on **PROJECTS** which can be grouped under **FOLDERS**

### Network Ingress and Egress

- **Normal Network**: Routes via internet to edge location _closets to destination_, available at _lower price_
- **Google**: Routes so traffic enters from @edge _closest to source_
  - Single global IP address and loadbalance worldwide
  - _AWS only supports Normal network_

### Pricing

- **Network Traffic**: Ingress Free, Egress charged per GB
  - _egress to a gcp service in a region is sometimes free_
- **Services**: Usage, Provisioned
- **Discounts**: Pay by second, Sustained Use discount, Cutomize compute resources or use out of box

### Security

- Seperation of duties
- Encryption at rest, in transition even within gcp network, DDoS, Google Frontend Test for Vulnerablilities
- _Recommends: Distrust the network_

## Useful commands

```sh
# Project Quota
gcloud compute project-info describe --project <project-id>
```

## Resources

### GCP Context

- [Google's Tools](https://en.wikipedia.org/wiki/Google_Data_Centers#Software)
- [Site Reliability Engineering (SRE) Book](https://landing.google.com/sre/book.html)
- [Interview with Lynn Langit](https://read.acloud.guru/serverless-superheroes-lynn-langit-on-big-data-nosql-and-google-versus-aws-f4427dc8679c)

### GCP Design and Structure

- [Data Center Tour #1](https://www.youtube.com/watch?v=XZmGGAbHqa0)
- [Data Center Tour #2 (360 Degree)](https://www.youtube.com/watch?v=zDAYZU4A3w0)
- [Regions Map](https://cloud.google.com/about/locations/#regions-tab)
- [Regions and Zones Docs](https://cloud.google.com/compute/docs/regions-zones/)
- [Network Map](https://cloud.google.com/about/locations/#network-tab)
- [Global Load Balancing](https://cloud.google.com/compute/docs/load-balancing/http/)
- [Network Pricing](https://cloud.google.com/compute/pricing#network)
- [Pricing Calculator](https://cloud.google.com/products/calculator/)
- [BeyondCorp](https://cloud.google.com/beyondcorp/)
- [GCP Security Design](https://cloud.google.com/security/security-design/)
- [Summary article on SRE Principles](https://medium.com/@jdavidmitchell/principles-of-site-reliability-engineering-at-google-8382b054e498)
- [Resource Quotas (Soft Limits)](https://cloud.google.com/compute/quotas)

### Compute

- [Compute Engine (GCE)](https://cloud.google.com/compute/)
  - [Creating Instances](https://cloud.google.com/compute/docs/instances/create-start-instance)
  - [Preemptible Instances](https://cloud.google.com/compute/docs/instances/create-start-preemptible-instance)
  - [Startup Scripts](https://cloud.google.com/compute/docs/startupscript)
  - [Service Accounts and Scopes](https://cloud.google.com/compute/docs/access/create-enable-service-accounts-for-instances)
- [Kubernetes Engine (GKE)](https://cloud.google.com/kubernetes-engine/)
- [App Engine (GAE)](https://cloud.google.com/appengine/)
- [Cloud Functions (GCF)](https://cloud.google.com/functions/)

### Storage, DB, and Transfer

- [Local SSD](https://cloud.google.com/compute/docs/disks/#localssds)
- [Persistent Disk](https://cloud.google.com/persistent-disk/)
- [Cloud SQL](https://cloud.google.com/sql/)
- [Cloud Spanner](https://cloud.google.com/spanner/)
- [Cloud Spanner Instance Configurations and Nodes](https://cloud.google.com/spanner/docs/instances)
- [BigQuery](https://cloud.google.com/bigquery/)
- [BigQuery Under the Hood](https://cloud.google.com/blog/big-data/2016/01/bigquery-under-the-hood)
- [Bigtable](https://cloud.google.com/bigtable/)
- [Cloud Datastore](https://cloud.google.com/datastore/)
- [Cloud Datastore Queries](https://cloud.google.com/datastore/docs/concepts/queries)
- [Firebase DBs](https://firebase.google.com/docs/database/rtdb-vs-firestore)
- [Cloud Storage](https://cloud.google.com/storage/)
- [Making Data Public](https://cloud.google.com/storage/docs/access-control/making-data-public)
- [Data Transfer Appliance](https://cloud.google.com/transfer-appliance/)
- [Storage Transfer Service](https://cloud.google.com/storage/transfer/)

### Networking

- [Google Domains](https://domains.google/#/)
- [Cloud DNS](https://cloud.google.com/dns/)
- [Static IPs](https://cloud.google.com/compute/docs/ip-addresses/reserve-static-external-ip-address)
- [Cloud Load Balancing (CLB)](https://cloud.google.com/load-balancing/)
- [Cloud CDN](https://cloud.google.com/cdn/)
- [Virtual Private Cloud (VPC)](https://cloud.google.com/vpc/)
- [Cloud Interconnect](https://cloud.google.com/interconnect/)
- [Cloud VPN](https://cloud.google.com/compute/docs/vpn/overview)
- [Dedicated Interconnect](https://cloud.google.com/interconnect/docs/details/dedicated)
- [Cloud Router](https://cloud.google.com/router/docs/)
- [CDN Interconnect](https://cloud.google.com/interconnect/docs/how-to/cdn-interconnect)

### Machine Learning / AI

- [Cloud Machine Learning Engine](https://cloud.google.com/ml-engine/)
- [My Coke Rewards Case Study](https://developers.googleblog.com/2017/09/how-machine-learning-with-tensorflow.html)
- [Cloud Vision API](https://cloud.google.com/vision/)
- [Cloud Speech API](https://cloud.google.com/speech/)
- [Cloud Natural Language API](https://cloud.google.com/natural-language/)
- [Cloud Translation API](https://cloud.google.com/translate/)
- [Dialogflow](https://cloud.google.com/dialogflow-enterprise/)
- [Cloud Video Intelligence API](https://cloud.google.com/video-intelligence/)
- [Cloud Job Discovery](https://cloud.google.com/job-discovery/)
- [Prediction API (Deprecated)](https://cloud.google.com/prediction/docs/end-of-life-faq)

### Big Data and IoT

- [Big Data Lifecycle](https://cloud.google.com/solutions/data-lifecycle-cloud-platform)
- [Cloud Internet of Things (IoT) Core](https://cloud.google.com/iot-core/)
- [Cloud Pub/Sub](https://cloud.google.com/pubsub/)
- [Cloud Dataprep](https://cloud.google.com/dataprep/)
- [Data Wrangling vs ETL](https://tdwi.org/articles/2017/02/10/data-wrangling-and-etl-differences.aspx)
- [Cloud Dataproc](https://cloud.google.com/dataproc/)
- [Cloud Dataflow](https://cloud.google.com/dataflow/)
- [Dataflow Shuffle](https://cloud.google.com/blog/big-data/2017/06/introducing-cloud-dataflow-shuffle-for-up-to-5x-performance-improvement-in-data-analytic-pipelines)
- [Cloud Datalab](https://cloud.google.com/datalab/)
- [Jupyter Notebook](https://jupyter.org/)
- [Cloud Data Studio](https://cloud.google.com/data-studio/)
- [Cloud Genomics](https://cloud.google.com/genomics/)

### Identity and Security

- [GCP Security Overview](https://cloud.google.com/security/)
- [Roles](https://cloud.google.com/iam/docs/understanding-roles)
- [Cloud Identity and Access Management (IAM)](https://cloud.google.com/iam/)
- [Hierarchical Access Control](https://cloud.google.com/iam/docs/resource-hierarchy-access-control)
- [Service Accounts](https://cloud.google.com/iam/docs/understanding-service-accounts)
- [Cloud Identity](https://support.google.com/a/answer/7319251)
- [Security Key Enforcement](https://cloud.google.com/security-key/)
- [Resource Manager](https://cloud.google.com/resource-manager/)
- [Resource Manager Hierarchy](https://cloud.google.com/resource-manager/docs/cloud-platform-resource-hierarchy)
- [Cloud Audit Logging](https://cloud.google.com/logging/docs/audit/)
- [Cloud Key Management Service (KMS)](https://cloud.google.com/kms/)
- [Cloud Identity-Aware Proxy (IAP)](https://cloud.google.com/iap/)
- [Cloud Security Scanner](https://cloud.google.com/security-scanner/)
- [Cloud Data Loss Prevention (DLP) API](https://cloud.google.com/dlp/)

### Operations and Management

- [Google Stackdriver](https://cloud.google.com/stackdriver/)
- [Stackdriver Chargeable Resources](https://cloud.google.com/stackdriver/pricing#chargeable-resources)
- [Stackdriver Monitoring](https://cloud.google.com/monitoring/)
- [Stackdriver Logging](https://cloud.google.com/logging/)
- [Stackdriver Error Reporting](https://cloud.google.com/error-reporting/)
- [Stackdriver Trace](https://cloud.google.com/trace/)
- [Stackdriver Debugger](https://cloud.google.com/debugger/)
- [Cloud Deployment Manager](https://cloud.google.com/deployment-manager/)

### Billing and Budget

- [Cloud Billing API](https://cloud.google.com/billing/docs/)
- [GCP Docs on Billing Export to BigQuery](https://cloud.google.com/billing/docs/how-to/export-data-bigquery)
- [GCP Docs on Budgets and Billing Alerts](https://cloud.google.com/billing/docs/how-to/budgets)
- [Billing Access Docs](https://cloud.google.com/billing/docs/how-to/billing-access)

### Development, Deployment and APIs

- [Cloud Source Repositories](https://cloud.google.com/source-repositories/)
- [Container Builder](https://cloud.google.com/container-builder/)
- [Container Registry (GCR)](https://cloud.google.com/container-registry/)
- [Cloud Endpoints](https://cloud.google.com/endpoints/)
- [Cloud Endpoints Architecture](https://cloud.google.com/endpoints/docs/openapi/architecture-overview)
- [Cloud Endpoints gRPC Transcoding](https://cloud.google.com/endpoints/docs/grpc/transcoding)
- [Apigee API Platform](https://cloud.google.com/apigee-api-management/)
- [Test Lab for Android](https://firebase.google.com/docs/test-lab/)

### GCP Solutions

- [Project Treehouse](http://gcp.solutions/)
- [API Hosting](http://gcp.solutions/diagram/API%20Hosting)
- [Jenkins on Kubernetes](http://gcp.solutions/diagram/Jenkins%20on%20k8s)
- [Log Processing](http://gcp.solutions/diagram/Log%20Processing)
- [Live Streaming](http://gcp.solutions/diagram/Live%20Streaming)
- [Shopping Cart Analysis](http://gcp.solutions/diagram/Shopping%20Cart%20Analysis)

### Learning GCP

- [Main Documentation](https://cloud.google.com/docs/)
- [Sample Architectures](http://gcp.solutions/)
- [YouTube Channel](https://www.youtube.com/user/googlecloudplatform)
- [GCP Blog](https://cloudplatform.googleblog.com/)
- [Free Trial Account](https://console.cloud.google.com/freetrial)
- [Codelabs](https://codelabs.developers.google.com/?cat=Cloud)
- [Tutorials](https://cloud.google.com/docs/tutorials)
- [Qwiklabs](https://google.qwiklabs.com/)
- [GCP Slack](https://gcp-slack.appspot.com/)
- [Google Certified Professional Cloud Architect](https://cloud.google.com/certification/cloud-architect)

### gsutil

- [Bucket Locations](https://cloud.google.com/storage/docs/bucket-locations)

### Rundown on gcloud

- [Overview Doc for gcloud](https://cloud.google.com/sdk/gcloud/)
- [Syntax of gcloud](https://cloud.google.com/sdk/gcloud/reference/)
- [Properties in gcloud](https://cloud.google.com/sdk/docs/properties)
- [Configurations in gcloud](https://cloud.google.com/sdk/docs/configurations)
- [Lab Commands List](https://raw.githubusercontent.com/ACloudGuru/gcp-cloud-engineer/master/compute-labs/connect-to-vm.txt)
- [Filters in gcloud](https://cloud.google.com/sdk/gcloud/reference/topic/filters)
- [Instance Metadata Reference](https://cloud.google.com/compute/docs/storing-retrieving-metadata)

### AcloudGuru Code Source

- [Course Resources GitHub Link](https://github.com/ACloudGuru/gcp-cloud-engineer.git)

### -Rearrange-

- [Service Accounts (incl. Scopes)](https://cloud.google.com/compute/docs/access/service-accounts)
- [GCE Instance Statuses](https://cloud.google.com/compute/docs/instances/checking-instance-status)
- [Long-Polling for Metadata Changes](https://cloud.google.com/compute/docs/storing-retrieving-metadata#waitforchange)
- [Hypervisor-Visible Metrics](https://cloud.google.com/monitoring/api/metrics_gcp#gcp-compute)
- [Agent-Visible Metrics](https://cloud.google.com/monitoring/api/metrics_agent)
- [Installing Stackdriver Agent](https://cloud.google.com/logging/docs/agent/installation)
- [List of Logs Sent by Agent (by Default)](https://cloud.google.com/logging/docs/agent/default-logs)

## Script to fetch Resources list from acg

```
[...document.getElementsByClassName('course-viewer--sidebar-course'), ...document.getElementsByClassName('course-viewer--resource-list')]
  .map((n) => {
        return [...n.querySelectorAll('h3'), ...n.querySelectorAll('a')].map((n) => {
          return (n.text ? '- [' : '### ') + (n.text||n.innerText || '').replace(/\s+/gm, ' ').trim() + (n.text ? '](' + n.href +')' : '')
        })
  })
  .reduce((acc, n) => acc.concat(n), [])
  .join("\n")
```
