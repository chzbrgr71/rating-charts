# rating-charts

Charts for AKS deployment of ratings app

## Setup

## Apps
```
helm upgrade --install rating-db ./rating-db --set mongo.image=chzbrgr71/rating-db --set mongo.imageTag=base

helm upgrade --install --reuse-values rating-api ./rating-api --set api.image=chzbrgr71/rating-api --set api.imageTag=base --set api.serviceType=LoadBalancer --set api.mongoURI=

helm upgrade --install rating-web ./rating-web --set web.image=chzbrgr71/rating-web --set web.imageTag=base --set web.serviceType=LoadBalancer

helm upgrade rating-web ./rating-web --set web.imageTag=cph
```

## ACR Creds

```
ACR_SERVER=
ACR_USER=
ACR_PWD=

kubectl create secret docker-registry acr-secret --docker-server=$ACR_SERVER --docker-username=$ACR_USER --docker-password=$ACR_PWD --docker-email=superman@heroes.com
```