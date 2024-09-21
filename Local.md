
### 本地端檢查 EKS-K8S 服務

0. **確認安裝以下工具：**
   - Terraform
   - Docker
   - Kubernetes 

1. **安裝 AWS CLI 並認證用戶：**  
   請參考 [AWS CLI 安裝指南](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)。

2. **進入 EKS-K8S cluster：**
   ```bash
   aws eks --region us-east-1 update-kubeconfig --name my-eks-cluster
   ```

3. **檢查 Pods 和 service ：**
   ```bash
   kubectl get pods,svc -n <namespace>
   ```

4. **預設port：**
   - **Nginx:** `8080`
   - **Nginx Exporter:** `9113`
   - **Grafana:** `3000`
   - **Prometheus:** `9090`

5. **本地虛擬機檢查 Prometheus（使用 port-forwarding）有沒有與nginx expoerter連結：**
   ```bash
   kubectl port-forward service/monitoring-kube-prometheus-prometheus -n monitoring 9090:9090
   ```
   然後在虛擬機瀏覽器中打開 [http://127.0.0.1:9090](http://127.0.0.1:9090)

  

6. **連結 Grafana 與 Prometheus**

   1. 查看 Grafana 與 Prometheus 的 Cluster IP：
      ```bash
      kubectl get svc -n monitoring
      ```
   2. 將 Grafana 的 Cluster IP 輸入瀏覽器：
      ```
      http://<Grafana Cluster IP>:3000
      ```
   3. 登入 Grafana，預設帳號為 `admin`，密碼使用以下指令：
      ```bash
      kubectl get secret --namespace monitoring grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo
      ```

   4. 進入 Grafana 介面後，前往 **「Settings」 > 「Data Sources」**。
   5. 點擊 **「Add data source」**，選擇 Prometheus。
   6. 在網址輸入欄位中，輸入 Prometheus 的 Cluster IP：
      ```
      http://<Prometheus Cluster IP>:9090
      ```
