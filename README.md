![image](https://github.com/tyiio445/eks-nginx/blob/main/image10135134.png)
# eks-nginx
使用 AWS 的 EKS服務整合了 Nginx、Grafana、Prometheus 和 Loki  
並通過 GitHub Actionsb 與 Terraform 進行 CI/CD 與 IAC 管理
# 環境配置
### 0. AWS IAM +建立 policy
   - 區選 us-east-1 並創建 IAM
   - 
### 1. 新增 github secrets 
   - Settings -> secrets -> actions
   - 新增 AWS_ACCESS_KEY_ID / AWS_ACCESS_SECRET_KEY
   
### 2. github actions workflow
   
### 3. 



本地端檢查 EKS-K8S 服務 
1. AWS CLI安裝與認證用戶
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
2. 進入EKS-K8S cluster
aws eks --region us-east-1 update-kubeconfig --name my-eks-cluster
3. 檢查pods services
kubectl get pods/svc -n namespace


  
    
  

   
