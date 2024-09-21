![image](https://github.com/tyiio445/eks-nginx/blob/main/image10135134.png)
# eks-nginx
使用 AWS 的 EKS服務整合了 Nginx、Grafana、Prometheus 和 Loki  
並通過 GitHub Actionsb 與 Terraform 進行 CI/CD 與 IAC 管理
# 環境配置
### 0. AWS IAM +建立 policy
   - 區選 us-east-1 並創建 IAM
   - policy詳見 [IAM-policy.md](https://github.com/tyiio445/eks-nginx/blob/main/IAM-policy.md)
### 1. 新增 github secrets 
   - Settings -> secrets -> actions
   - 新增 AWS_ACCESS_KEY_ID / AWS_ACCESS_SECRET_KEY
   
### 2. github actions workflow
   - Github Repo介面 > actions > 選取 Deploy to EKS 選擇run the work flow
### 3. 本地端操作EKS-K8S cluster詳見 [Local.md](https://github.com/tyiio445/eks-nginx/blob/main/Local.md)

### 4. 錯誤
   - terraform destroy時無法刪除
   - 請先把AWS EC2 -> loadbalancer刪除掉即可









  
    
  

   
