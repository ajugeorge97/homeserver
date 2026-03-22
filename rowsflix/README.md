# Create secret from your .env file
kubectl create secret generic rowsflix-secret --from-env-file=.env

# Apply deployment
kubectl apply -f deployment.yaml
Check status:



