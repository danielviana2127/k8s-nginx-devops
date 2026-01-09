# 🚀 Kubernetes NGINX DevOps Project

Este projeto demonstra a implantação de uma aplicação **NGINX** em um cluster **Kubernetes**, seguindo boas práticas de **DevOps**, organização de manifests e foco em aprendizado prático.

O repositório foi estruturado para ser **simples**, **funcional** e ao mesmo tempo **alinhado com padrões de mercado**, ideal para estudos, portfólio e evolução futura (CI/CD, Kustomize, Ingress, etc.).

---

## 🧱 Arquitetura do Projeto

```
k8s-nginx-devops
│── README.md
└── base/
    ├── deployment.yml
    ├── service.yml
    ├── configmap.yml
    └── secret.yml
```

### 📦 Descrição dos Componentes

* **Deployment**

  * Responsável por criar e gerenciar os Pods do NGINX
  * Define número de réplicas, imagem do container, recursos e probes

* **Service (NodePort)**

  * Expõe o NGINX para acesso externo
  * Utilizado em ambiente local com Minikube

* **ConfigMap**

  * Armazena variáveis de configuração da aplicação
  * Exemplo: ambiente da aplicação (`APP_ENV`)

* **Secret**

  * Armazena dados sensíveis (ex: usuário de banco)
  * Valores codificados em Base64

---

## 🛠️ Tecnologias Utilizadas

* Kubernetes
* NGINX
* Minikube
* kubectl
* YAML

---

## 📋 Pré-requisitos

Antes de iniciar, certifique-se de ter instalado:

* Docker
* Minikube
* kubectl

Verifique as versões:

```bash
kubectl version --client
minikube version
```

---

## ▶️ Como Executar o Projeto

### 1️⃣ Iniciar o Minikube

```bash
minikube start
```

### 2️⃣ Aplicar os manifests Kubernetes

Na raiz do projeto:

```bash
kubectl apply -f base/
```

### 3️⃣ Verificar os recursos criados

```bash
kubectl get pods
kubectl get svc
```

Você deve ver os Pods do NGINX com status **Running**.

---

## 🌐 Acessando a Aplicação (Minikube)

Como o projeto utiliza **Service do tipo NodePort**, o acesso correto no Minikube é feito com:

```bash
minikube service nginx-service
```

Esse comando irá:

* Abrir o navegador automaticamente
* Ou exibir a URL correta para acesso

Exemplo:

```
http://127.0.0.1:xxxxx
```

---

## 🔍 Testes e Debug

### Ver logs do Pod

```bash
kubectl logs <nome-do-pod>
```

### Acessar o container

```bash
kubectl exec -it <nome-do-pod> -- sh
```

### Teste interno do NGINX

```bash
kubectl exec -it <nome-do-pod> -- curl localhost
```

---

## ✅ Boas Práticas Aplicadas

* Organização clara dos manifests
* Uso de labels padronizadas
* Separação de ConfigMap e Secret
* Resource requests e limits
* Readiness e Liveness Probes
* Uma única fonte de verdade (`base/`)

---

## 📈 Próximos Passos (Evolução do Projeto)

Este projeto está pronto para evoluir para:

* 🔧 Kustomize (ambientes `dev` e `prod`)
* 🌍 Ingress Controller
* 🔐 TLS / HTTPS
* 🔄 CI/CD com GitHub Actions
* 📦 Helm Charts

---

## 👨‍💻 Autor

**Daniel Viana**
Projeto de estudo focado em Kubernetes e DevOps.

---

## ⭐ Conclusão

Este repositório representa uma base sólida para quem está aprendendo Kubernetes na prática, com foco em organização, clareza e boas práticas reais utilizadas no mercado.

Sinta-se à vontade para evoluir, adaptar e expandir este projeto 🚀
