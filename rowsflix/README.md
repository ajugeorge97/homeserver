# Create secret from your .env file
[source code](https://github.com/cristofloyd/RowsFlix)

```env
TG_API_ID=your_api_id
TG_API_HASH=your_api_hash
BOT_TOKEN=your_bot_token
OWNER_ID=your_telegram_user_id
JELLYFIN_ROOT=/media #this should be the same folder mounted to the jellyfin service
```

```kubectl create secret generic rowsflix-secret --from-env-file=.env```

# Apply deployment
kubectl apply -f deployment.yaml
Check status:



