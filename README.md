# ElasticSearch-Cluster
ES 集群管理（集群规划、集群搭建、集群管理）
[root@master02 ~]# kubectl get pod -n elkstack -o wide
NAME                            READY     STATUS    RESTARTS   AGE       IP             NODE
es-data-59bcc4c66d-gbqfl        1/1       Running   0          23m       10.244.0.98    master02
es-data-59bcc4c66d-n78kh        1/1       Running   0          23m       10.244.3.229   node02
es-ingest-7c58f98565-77t94      1/1       Running   0          23m       10.244.1.119   master03
es-ingest-7c58f98565-8hxp7      1/1       Running   0          23m       10.244.2.115   master01
es-ingest-7c58f98565-txnc5      1/1       Running   0          23m       10.244.3.230   node02
es-master-5d87bd4988-2n28h      1/1       Running   0          23m       10.244.3.231   node02
es-master-5d87bd4988-crtsr      1/1       Running   0          23m       10.244.1.120   master03
es-master-5d87bd4988-d2m47      1/1       Running   0          23m       10.244.0.99    master02
k8s-logstash-59cf8bdcc9-j6484   1/1       Running   0          23m       10.244.2.117   master01
k8s-logstash-59cf8bdcc9-j97b7   1/1       Running   0          23m       10.244.3.233   node02
k8s-logstash-59cf8bdcc9-lj96v   1/1       Running   0          23m       10.244.0.100   master02
kibana-5f5bdb4f5f-2kk2c         1/1       Running   0          23m       10.244.2.116   master01
kibana-5f5bdb4f5f-fqz5f         1/1       Running   0          23m       10.244.3.232   node02
[root@master02 ~]# kubectl get svc -n elkstack -o wide   
NAME                       TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE       SELECTOR
elasticsearch-data-svc     ClusterIP   10.111.221.29   <none>        9200/TCP         23m       component=elasticsearch,role=data
elasticsearch-ingest-svc   NodePort    10.99.155.143   <none>        9200:30625/TCP   23m       component=elasticsearch,role=ingest
elasticsearch-master-svc   ClusterIP   None            <none>        9300/TCP         23m       component=elasticsearch,role=master
kibana                     NodePort    10.102.249.93   <none>        5601:30421/TCP   23m       component=kibana
[root@master02 ~]# 
