本地端檢查 EKS-K8S 服務   
0. 確認安裝terraform , docker , k8s  
1. AWS CLI安裝與認證用戶  
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html  
2. 進入EKS-K8S cluster  
aws eks --region us-east-1 update-kubeconfig --name my-eks-cluster  
3. 檢查pods services  
kubectl get pods/svc -n namespace  
4. 預設各service port  
   Nginx : 8080  
   Nginx exporter : 9113  
   Grafana : 3000  
   Prometheus : 9090  
5. 本地虛擬機確認prometheus  
   kubectl port-forward service/monitoring-kube-prometheus-prometheus -n monitoring 9090:9090  
   之後登入 http://127.0.0.1:9090  
6. 
