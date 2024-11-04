# ms_configs

This is a Kubernetes configuration for two services of microservices project:
* [Order Service](https://github.com/SvetlanaVys/ms_order)
* [Delivery Service](https://github.com/SvetlanaVys/ms_delivery)

## Project Structure

```bash

├── ms-delivery/
│   ├── configmap.yaml
│   ├── delivery_app.yaml
│   ├── postgres-secret.yaml
│   └── postgres.yaml
├── ms-order/
│   ├── configmap.yaml
│   ├── order_app.yaml
│   ├── postgres-secret.yaml
│   └── postgres.yaml
├── ingress.yaml
├── kustomization.yaml
├── namespace.yaml
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

### Step 2: Enable ingress

For instance, if you use Minikube environment, run the following command:

```bash
 minikube addons enable ingress
```
   
### Step 3: Deploy the Services

Run the following command to deploy the services to the 
Kubernetes cluster:
```bash
 kubectl apply -k .
```

### Step 4: Access the Services via Swagger
After the Ingress is set up, you can access the Swagger documentation for both services using the following URLs:
   - https://marketplace.svysk.com/ms-order/swagger-ui/index.html
   - https://marketplace.svysk.com/ms-delivery/swagger-ui/index.html
