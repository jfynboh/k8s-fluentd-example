# k8s-fluentd-example

Quickstart:

1. Create Container (see container/README.md):
cd container
docker build . -t myrepository/myfluentd:latest \
  && docker push myrepository/myfluentd:latest


2. create/copy your fluent.conf.


3. Create K8S secrets, (you can add the fluent.conf file, gcp certs, etc.
kubectl -n mynamespace create secret generic mysecret --from-file=fluent.conf=./fluent.conf

4. Adjust deployment descriptor (k8s/fluentd-deployment.yaml).
Change  myrepositiory/myfluentd to reflect your reporpitory / image name / tags

5. Deploy to k8s
kubectl -n mynamespace apply -f k8s/fluentd-deployment.yamml

