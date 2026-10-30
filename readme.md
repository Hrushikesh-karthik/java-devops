
pom.xml
   ↓
Maven builds Java application
   ↓
JAR
   ↓
Dockerfile
   ↓
Docker builds container image
   ↓
Kubernetes YAML
   ↓
Kubernetes runs containers

hostname I
kubectl port-forward --address=0.0.0.0 svc/argocd-server -n argocd 9090:443

kubectl -n argocd get secret argocd-initial-admin-secret \
  -o jsonpath="{.data.password}" | base64 -d
echo

DAST with OWASP ZAP
Run the Juice Shop Application

docker run -d \
  --name juice-shop \
  -p 3000:3000 \
  bkimminich/juice-shop
Open in browser:

localhost:3000
Scan target by running ZAP from cli

docker run --rm \                                                                                      ✔  8509  15:33:58
  -v "$(pwd):/zap/wrk" \
  -t ghcr.io/zaproxy/zaproxy:stable \
  zap-baseline.py \
  -t http://host.docker.internal:3000 \
  -r zap-report.html
Scan target by running ZAP from UI

docker run -it \                                                                             SIGINT(2) ↵  8509  15:36:05
  -p 8080:8080 \
  ghcr.io/zaproxy/zaproxy:stable \
  zap-webswing.sh
Open Zap UI:

http://localhost:8080/zap
