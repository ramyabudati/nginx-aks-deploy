# nginx-into-aks

## azure connect method
  * To connect azure AKS, used service principal.
  * The below values are updated at "github repository secrets " section
    * AZURE_CLIENT_ID
    * AZURE_CLIENT_SECRET
    * AZURE_TENANT_ID
   

## project summary

* to demonstrate build and deployment(CI/CD) of appplciations, used "nginx" web page
* Created __Dockerfile__ and __index.html__ , whenever any change/push to __github repository__, it will automatically build the application, push docker image to __ACR__ ,
* Automatically deploy into __AKS__ cluster by using __helm__ chart.
* __helm__ chart location [refer here](./deployment-scripts/dev/helm)

### Notes
* At the time of creating __AKS cluster__ intergrated __ACR__ registery. Due to that not created any __imagepullsecrets__ in deployment.yaml file.
* __Application gateway ingress__ created and attached to __AKS__ cluster
* Applicaiton is access by __applciation gateway__ public IP.
