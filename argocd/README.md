# ARGOCD
##### Install
- https://argo-cd.readthedocs.io/en/stable/getting_started/ <br>
- ```
   kubectl create namespace argocd
   kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
   ```

##### Port forward `argocd server` <br>
- kubectl port-forward -n argocd svc/argocd-server 8080:443
- `localhost:8080` to access argocd

##### log in to argocd
- user: admin <br>
- password: `argocd-initial-admin-secret` (can be found here) <br>
- `kubectl get secret argocd-initial-admin-secret -n argocd -o yaml` <br>
- echo <PASSOWRD> | base64 --decode <br>   "this will give us the password"
```
The initial password for the admin account is auto-generated and stored as clear text in the field password in a secret named argocd-initial-admin-secret in your Argo CD installation namespace. You can simply retrieve this password using the argocd CLI:

`argocd admin initial-password -n argocd`
```

##### Configure ArgoCD to conect to the configuration file
