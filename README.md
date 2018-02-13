# rating-charts

Charts for AKS deployment of ratings app

helm upgrade --install db ./rating-db --set mongo.image=chzbrgr71/rating-db --set mongo.imageTag=base

helm upgrade --install api ./rating-api --set api.image=chzbrgr71/rating-api --set api.imageTag=base --set api.serviceType=LoadBalancer

helm upgrade --install web ./rating-web --set web.image=chzbrgr71/rating-web --set web.imageTag=base --set web.serviceType=LoadBalancer