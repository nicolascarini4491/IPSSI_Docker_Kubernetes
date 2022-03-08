kubectl apply -f .\lamp-vp.yaml
kubectl apply -f .\lamp-claim.yml
kubectl apply -f .\lamp-configmap.yaml
kubectl apply -f .\lamp-secret.yml
kubectl apply -f .\lamp-wp.yml
kubectl apply -f .\lamp-service.yml

Récuperer le nom du pod lamp-wp:
- kubectl get pods

Copier le nom du pod puis entrer:
- kubectl cp index.php lamp-wp-d5c9447b9-7vj25:/app -c httpd-php-container

Ouvrir un navigateur puis allez sur http://localhost


Pour clean:

kubectl delete deployment lamp-wp
kubectl delete service lamp-service
kubectl delete service mysql-service
kubectl delete secret mysql-secret
kubectl delete configmap php-config
kubectl delete pvc lamp-claim
kubectl delete pv lamp-vp

