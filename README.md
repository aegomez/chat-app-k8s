# chat-app-k8s
Kubernetes configuration files for the chat with no name.

## Deployment

```
kubectl apply -f .
```

## Secrets

Some env variables should be passed to the pods as secrets. The required secrets are: 

```sh
name: auth-db-secret
keys:
  # MongoDB configuration 
  MONGO_INITDB_ROOT_USERNAME
  MONGO_INITDB_ROOT_PASSWORD
  MONGO_INITDB_DATABASE

name: auth-service-secret
keys:
  JWT_SECRET # The secret to encrypt jsonwebtokens
  MONGODB_URI # MongoDB full URI (include username and password)

name: conv-db-secret
keys:
  # MongoDB configuration 
  MONGO_INITDB_ROOT_USERNAME
  MONGO_INITDB_ROOT_PASSWORD
  MONGO_INITDB_DATABASE

name: user-db-secret
keys:
  # MongoDB configuration 
  MONGO_INITDB_ROOT_USERNAME
  MONGO_INITDB_ROOT_PASSWORD
  MONGO_INITDB_DATABASE

name: user-service-secret
keys:
  # Cloudinary API Key+Secret
  # Only required if using the default image uploader
  # when trying to chage the default avatar.
  CLOUDINARY_URL
  
```

## Author
Adrian Gomez.

## LICENSE
[MIT](LICENSE).
