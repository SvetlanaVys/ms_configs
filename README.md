# ms_configs

This is a Kubernetes configuration for two services of microservices project:
* [Order Service](https://github.com/SvetlanaVys/ms_order)
* [Delivery Service](https://github.com/SvetlanaVys/ms_delivery)

## Project Structure

```bash

├── ms-delivery/
│   ├── deployment.yaml
│   └── service.yaml
├── ms-order/
│   ├── deployment.yaml
│   └── service.yaml
├── ingress.yaml
└── README.md
```

## How to Run the Application
### Step 1: Update the Hosts File
You need to map the domain name to your local Kubernetes cluster IP.
 - **MacOS**: Edit the hosts file by running the following command:
    ```bash
    sudo nano /etc/hosts
    ```
 - Windows: Manually edit the file located at C:\Windows\System32\drivers\etc\hosts.
 - Add the following entry to your hosts file:
    ```bash
   <Kubernetes cluster IP>  marketplace.svysk.com
    ```
   
### Step 2: Deploy the Services

For each service (ms-delivery and ms-order), run the following commands to deploy the services to your 
Kubernetes cluster:
```bash
 kubectl apply -f deployment.yaml
 kubectl apply -f service.yaml
```

### Step 3: Apply Ingress Configuration
Once both services are running, apply the Ingress configuration to expose the services through a domain:
```bash
kubectl apply -f ingress.yaml
```
### Step 4: Access the Services via Swagger
After the Ingress is set up, you can access the Swagger documentation for both services using the following URLs:
   - https://marketplace.svysk.com/ms-order/swagger-ui/index.html
   - https://marketplace.svysk.com/ms-delivery/swagger-ui/index.html
