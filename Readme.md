## Deploy on GKE

kubectl create deployment hello-app --image=gcr.io/umeshkumhar-1/hello-app:1.0

kubectl expose deployment hello-app --type LoadBalancer --port 80 --target-port 8080



## Deploy on Cloud Run

gcloud run deploy hello-app --image gcr.io/umeshkumhar-1/hello-app:1.0 \
--region us-central1 --allow-unauthenticated





## Rollout on Cloud Run

gcloud run deploy hello-app --image gcr.io/umeshkumhar-1/hello-app:2.0 --region us-central1   --no-traffic  --tag v2-green

gcloud run services update-traffic hello-app  --region us-central1  --to-tags v2-green=100
