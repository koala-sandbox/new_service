# new_service

This repo was created with [KoalaOps](https://app.koalaops.com/)

## Description



## How to run locally?

```
python3 -m venv venv && source venv/bin/activate;
pip3 install -r requirements.txt;
python3 run.py
```

## How to run with Docker?

```
docker build -t new_service:latest .
docker run -p:5030:8080 new_service:latest
```

Server will listen at http://localhost:5030

## K8s Configuation and Deployment

On service creation Koala created for you 3 k8s resources to use:

- deployment.yaml
- service.yaml
- ingress.yaml

Those are located in the [deploy](deploy) directory and should be applied with kustomize. For example:

### In Production run: 

```
cd deploy
kubectl apply -k overlays/prod
```

### In Dev run: 

```
cd deploy
kubectl apply -k overlays/dev
```

