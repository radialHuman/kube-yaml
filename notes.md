## Source : [YAML File Explained For Kubernetes with Live DEMO](https://www.youtube.com/watch?v=Qyfqt0uOHsk)
### Exmaple is for two yaml files for nginx deployment:
    - deployment : for main applciation pod
    - service : pod for providing n/w configuration

### Structure

|section | name | values | reason |
|-|-|-|-|
|apiversion section | apiversion | v1 or apps/v1  | specific api in kub to create an object. Each api in Kub contains core objects. so the versionof which api needs to be sued is mentioned here. check which api version needs to be used for the usecase. where to find it? |
| kind section |kind| deployment or service or anything | type of file being created or its purpose |
| metadata |  | | for info about the file or section |
| metadata | name | nginx-deployment nginx-service | your own name for the purpose of the service |
| metadata | labels | app : nginx, environment : production| for identification kv pair, can be multiple pairs, can they be random or some key words are fxied?|
| specs | | | specification fo the pod  |
| specs  | replicas | 1 2 3 ... | # of pods with the same configuration to be created for fallback|
| sepcs | selector | matchLables-> app:nginx | used for grouping, in case there are multiple deployment files pointing to one service file in that scenario, this will link the files using app :name of the app. example from service to metadata -> labels and template -> metadata-> labels |
| specs | template | metadata -> labels -> app:nginx | blueprint for pod  |
| specs|  template| spec -> containers -> - name : nginx \n image : nginx:1.4.2 \n ports -> -containerPort : 80| this spec is for the continaer details, which will be info about the container created in registry or repository. it will have the name of the container, the image path, and which port its exposing |
| spec | ports | - port : 80 \n nodePort : 7800 | this is on the service side where the port is same as the exposed port in deployment and the nodeport is between 30k to 32768 to access applcaition from each node? |
| | | | |

```cli
#to deploy the deployment file
kubectl apply -f nginx-deploy.yaml
kubectl apply -f nginx-service.yaml

# to see the pods after deployment
kubectl get pods

# to check service
kubectl get svc
```

---

## Source : []()
