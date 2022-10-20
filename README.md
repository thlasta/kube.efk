# kube.efk
EKF components get deployed as follows,

Fluentd:- Deployed as daemonset as it need to collect the container logs from all the nodes. It connects to the Elasticsearch service endpoint to forward the logs.
Elasticsearch:- Deployed as statefulset as it holds the log data. We also expose the service endpoint for Fluentd and kibana to connect to it.
Kibana:- Deployed as deployment and connects to elasticsearch service endpoint.

https://devopscube.com/setup-efk-stack-on-kubernetes/

echo "# kube.efk" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:thlasta/kube.efk.git
git push -u origin main


# Repo clonen
git clone git@github.com:thlasta/kube.efk.git

# Repo auschecken/holen
git pull git@github.com:thlasta/kube.efk.git

# Jump one folder up, and apply to the whole folder:
kubectl apply -f efk/

# Namespace "monitoring" anlegen
kubectl create namespace monitoring