### IAM Policies for EKS 

配置 EKS 和 EC2 所需的 IAM Policy :

- **AmazonEC2ContainerRegistryReadOnly**
- **AmazonEC2FullAccess**
- **AmazonEKS_CNI_Policy**
- **AmazonEKSClusterPolicy**
- **AmazonEKSServicePolicy**
- **AmazonEKSWorkerNodePolicy**
- **AmazonVPCFullAccess**
- **IAMFullAccess**

### 與自定義的IAM 

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "eks:CreateCluster",
                "eks:DescribeCluster",
                "eks:DeleteCluster",
                "eks:ListClusters",
                "eks:UpdateClusterConfig",
                "eks:UpdateClusterVersion",
                "eks:CreateNodegroup",
                "eks:DescribeNodegroup",
                "eks:DeleteNodegroup",
                "eks:ListNodegroups"
            ],
            "Resource": "*"
        }
    ]
}
```
