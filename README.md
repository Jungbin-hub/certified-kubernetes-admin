# certified-kubernetes-admin
CKA 실습 및 학습 기록
# CKA Day 1 - 기본 개념 & kubectl 명령어 실습

## ✅ 오늘 배운 내용
- Kubernetes 아키텍처 개요
- 클러스터 접근 (`kubectl`)
- 기본 Pod 생성 및 관리
- Namespace 생성 및 활용

## 🧪 실습 명령어

```bash
# 현재 context 확인
kubectl config view
kubectl config current-context

# 네임스페이스 생성
kubectl create ns practice-ns

# Pod 생성 (nginx)
kubectl run nginx --image=nginx -n practice-ns

# 생성된 Pod 확인
kubectl get pods -n practice-ns

---

### 2. `nginx-pod.yaml`  
> 수동으로 Pod 생성해보고 싶을 때 사용

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
  namespace: practice-ns
spec:
  containers:
  - name: nginx
    image: nginx
