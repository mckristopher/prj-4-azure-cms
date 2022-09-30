# Write-up : Comparison of VM vs App Service as Compute Service for CMS App

### Analysis.

*Scalability:*
- Azure AppServices are auto scalable but have a limitation of 14GB of storage
- Azure VMs have high scaling capacity but it is labor intensive
- For our CMS, Azure App Services offer the desired scalability along with efficiency

*Availability:*
- Although both App Services and Azure VMs provide high availability, VMs provide more options between compute and memory optimized as per the purpose
- Our CMS requires limited computation and memory at the moment, which is sufficed by an App Service

*Workflow:*
- Azure App Services is a PaaS service, that brings about ease in setting up and maintaining a hosted application.
    App Services helps to easily get the app up and running directly from a git repo. It also enables a CI / CD pipeline configuration to make future deployments efficient.
- Azure VMs is a IaaS and involves a lot of effort from the developer to setup the app and to make future deployments.
The repos have to be moved manually or git setup has to be configured. In this case only the machine is provided and everything else has to be handled by the developer
- For our CMS, since this is a pure web app, an Azure App Service will be the best option to handle the workflow, allowing easy setup and maintenance

*Costs:*
- Azure App Services can be expensive since there is no Pay-as-you-go option and charges are made even when an app is not running. The Basic App Service plan with 1.75 GB storage is estimated to be 946 INR / month.
- Azure VMs are only charged based on disk costs when stopped. The Basic VM cost with 1GB storage is estimated at 589 INR / month
- In the case of the CMS, assuming that the app will continue to run and will be limited to 1GB of storage, a VM might be the better option in terms or expenses.

### Conclusion

The current requirements of the CMS app are conveniently met by using an Azure App Service, by providing quick setup and ease of maintaining the application. The compute and memory capacity provided by App Service is also adequate

### App changes to use Azure VM

** When a large number of users are using the CMS and there is a high level of activity, an Azure App Service might not provide the necessary computational power. In this case, an Azure VM with higher number of CPUs can prove effective to maintain latency.