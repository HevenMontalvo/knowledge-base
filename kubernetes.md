---
topic: Kubernetes / DevOps
subtopic: Troubleshooting
tools: [kubectl, docker]
---

# Kubernetes commands

## 🚀 Basic comandos
| Comando | Descripcion |
| :--- | :--- |
| `kubectl get pods` | List pods in the current namespace. |
| `kubectl describe pod [name]` | to see events related the pod |
| `kubectl set image deployment/[dep] [cont]=[img]` | update image for deployment. |
| `kubectl config view` | view config current context. |
| `kubectl explain pods --recursive` | Explain pods. |
| `kubectl explain pod.spec.restarPolicy` | Explain a policy. |
| `kubectl apply -f pod.yml` | deploy a pod from yaml. |
| `kubectl exec hello-pod -- ps aux` | running commands in Pods |
| `kubectl exec -it hello-pod -- sh` | connect to pod |



## 🛠 Troubleshooting

### Error: `ErrImagePull` o `ImagePullBackOff`
- **Cause:** invalidad image name.
- **Solucion:** Check the spelling in the creation command or in the YAML manifest.

## 💡 Tips"
- Use the `-w` flag to monitor changes in real time.
- Always check which node the pod is running on using `-o wide`.

## 🔗 links
- [Oficial K8s doc - Pods](https://kubernetes.io/docs/concepts/workloads/pods/)
- [[02-devops/kubernetes/indice-k8s|Volver al Indice de Kubernetes]]