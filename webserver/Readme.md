curl --user user:00T3mp0ral00 --header "host: secure-webserver" http://192.168.49.2:31596/index.html 

kubectl exec -ti netools -- curl --user user:00T3mp0ral00 secure-webserver  
default index



apiVersion: v1
data:
  .htpasswd: dXNlcjokYXByMSRsNTlzcExITSROcXVVdjB5UEtuTS45alVXRlp4Q0cwCg==
kind: Secret
metadata:
  creationTimestamp: null
  name: secure-webserver-htpasswd