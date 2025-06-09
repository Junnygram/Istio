## 🔹 Introduction to Microservices

### ❓ The Big Question

**Ever wonder how apps like Instagram, Netflix, or Amazon work smoothly with millions of users?**
It’s not one giant app—it’s a team of _small, independent services_ working together. That’s **microservices**.

---

## 🏛️ Before Microservices: The Monolith

- Applications used to be built as **monoliths**.

  - Everything was packed into **one system**: UI, business logic, database access.

- Example: In an old-school e-commerce app:

  - User management, product catalog, payment, and order tracking all ran as **one big app**.

### 🚨 Problems with Monoliths

- **Scaling is hard**: You can't scale just one part, like payments. You must scale everything.
- **Fragile codebase**: A small change can break the whole app.
- **Team issues**: Developers working on different features can clash easily.

---

## 🔧 Enter Microservices

**Microservices = breaking the app into small, independent services**
Each one handles a **specific task**, like:

- 🔐 Authentication
- 🛒 Product catalog
- 💳 Payments
- 📦 Order tracking

### 🛠 Benefits:

- **Scalability**: Scale what’s needed, not the whole app.
- **Fault isolation**: One service fails? The rest keep running.
- **Flexibility**: Use the best language or tech for each service.
- **Faster updates**: Teams can build and deploy services independently.

---

## 📡 How Do Microservices Talk?

- **Lightweight protocols** like HTTP or message queues
- Each service is **independent**, can use **different tech stacks**

---

## 📦 Packaging with Containers

- Microservices are often put into **containers** using **Docker**
- Containers are:

  - Portable 🧳
  - Consistent across environments ⚙️
  - Isolated 🛡️

---

## 🚀 Managing Containers at Scale

- Use **Kubernetes** to:

  - Deploy
  - Scale
  - Monitor & manage containers

- Kubernetes helps manage **hundreds or thousands of microservices**

---

## ⚠️ Microservices Challenges

- How do services **communicate efficiently**?
- How do we **monitor** all services?
- How do we ensure **security** and **reliability**?

---

## 🕸️ Solution: Service Mesh

> A **service mesh** handles all that complexity.
> It simplifies communication, observability, and security across microservices.

---

### ✅ Up Next: Intro to Service Mesh!

---

---

## 🕸️ What Is a Service Mesh (And Why It Matters)

### 🌆 Imagine This...

Microservices are like **a bustling city**:

- Each **building = a service**
- Each **road = communication path**

Without traffic signals or GPS? Total **chaos**.
That’s where a **service mesh** comes in — it’s the **traffic system** for your microservices.

---

## 🚦 What a Service Mesh Does

A service mesh:

- **Manages how services communicate**
- Adds **proxies** (tiny helpers) to handle:

  - Traffic control
  - Security
  - Observability (monitoring)

These proxies sit **next to** your services — like a **motorcycle sidecar** 🏍️
This is called a **sidecar configuration**.

---

## 🧠 How It Works

### 🔹 Two Key Components:

1. **Control Plane** 🧭

   - Think of it as the **brain**.
   - Sets the rules: how services should talk.

2. **Data Plane** 📦

   - Made of **proxies**.
   - They follow the rules and handle real-time traffic.

💡 These proxies ensure that communication is:

- Smooth ✅
- Secure 🔒
- Reliable 📶

---

## 🆕 What’s Changing?

- New models like **Ambient Mesh** remove the sidecar model for more flexibility and performance.

---

## 🧩 Why Do We Need a Service Mesh?

### 1. **Traffic Management**

- Microservices = tons of communication paths.
- Like rush hour 🚗🚕🚙 on a highway — requests can get:

  - Delayed
  - Lost
  - Bottlenecked

A service mesh helps **route traffic efficiently**.

---

### 2. **Security**

Without a service mesh:

- Every service must handle **its own security** (encryption, access rules).
- More services = more room for mistakes ⚠️

With a service mesh:

- Security is **centralized and consistent** across all services.

---

### 3. **Observability**

- With a few services, tracking is easy.
- With **dozens or hundreds**, it’s like watching every street in a city 🌃

A service mesh gives you **full visibility**:

- What's working
- What’s failing
- Where traffic is going

---

## 🛡️ Meet Istio

- Istio is one of the most popular service meshes.
- It **solves traffic, security, and visibility problems** for microservices.

---

### ▶️ Coming Next: Deep Dive into **Istio**

---

## 🚀 Introducing Istio: The Game-Changer for Microservices

### 🧠 Recap:

We’ve seen the chaos of microservices and how service meshes help — now meet **Istio**, one of the **most popular service mesh tools** out there.

---

## 🧰 What Is Istio?

- 🧩 **Open-source** service mesh
- 🔐 Connects, secures, and monitors your services
- 🚫 No need to **rewrite your code** — just plug and go!

---

## 💡 Why Istio Stands Out

### 🔒 1. **Secure Communication**

- Encrypts traffic between services
- Uses **authentication + encryption**
- Think of it like every service having its **own lock and key**

---

### ⚖️ 2. **Automatic Load Balancing**

- Prevents any one service from getting overwhelmed
- Keeps your system **smooth and responsive**

---

### 🧭 3. **Traffic Control**

- Fine-grained control over:

  - Routing
  - Retries on failed requests
  - A/B testing or traffic splitting

---

### 👁️ 4. **Observability**

- Deep insights via:

  - Logs
  - Metrics
  - Distributed Tracing

- Makes it easy to **spot and fix issues fast**

---

## 🛠️ Istio Architecture: How It Works

### 1. **Data Plane** 🛰️ (Where the traffic flows)

- Powered by **Envoy proxies**
- Handles:

  - Routing
  - Load balancing
  - Encryption
  - Resilience (retries, timeouts)

📦 Envoy = the **messenger** carrying your service traffic safely.

---

### 2. **Control Plane** 🎮 (Where decisions are made)

- Managed by **Istiod**
- Configures Envoy proxies
- Sets:

  - Traffic rules
  - Security policies
  - Service discovery (who talks to who)

🧠 Istiod = the **brain** behind the traffic system.

---

## ⚙️ Deployment Options in Istio

### 1. **Sidecar Mode** 🏍️

- Envoy runs **next to each service**
- Acts like a **personal assistant** for traffic
- Handles everything: routing, security, etc.

---

### 2. **Ambient Mode** ☁️

- Newer, **lightweight model**
- One proxy per **node**, optionally per **namespace**
- Great for **large-scale** setups — reduces overhead

---

---

## 🧭 Istio Data Plane Modes: Sidecar vs Ambient

Istio offers **two primary data plane modes** to manage traffic between services:

### 1. **Sidecar Mode**

- **Architecture**: Each pod in your Kubernetes cluster has its **own Envoy proxy sidecar**.
- **Responsibilities**: Handles **routing, security, and monitoring** from **Layer 4 to Layer 7**.
- **Benefits**:

  - Each pod has **its own identity** and **encryption**.
  - Fine-grained **traffic management** and **observability**.
  - Like giving each pod its **own bodyguard**.

- **Drawbacks**:

  - High **resource usage** (CPU & memory), especially in large clusters.
  - Operational overhead for **upgrades and restarts**.

---

### 2. **Ambient Mode** _(Newer, more efficient)_

- **Architecture**:

  - **No sidecars** in pods.
  - Uses two layers:

    - **Secure Overlay Layer**: Managed by `ztunnel`, a lightweight data plane running on **each node**, providing **zero-trust security** and encrypted connections.
    - **L7 Processing Layer**: Uses **waypoint proxies** for advanced Layer 7 features (e.g., traffic splitting, fault injection).

- **Benefits**:

  - Lower **memory/CPU usage**.
  - **Simplifies updates** (no pod restarts).
  - **Flexible**: Start with basic security and **add features as needed**.

- **Drawbacks**:

  - Still **relatively new**; some advanced features may require **manual config**.

---

> ✅ **Key Insight**: Ambient mode **decouples** security and traffic management responsibilities, making deployments more **resource-efficient and flexible**.

---

### ▶️ Up Next: A Closer Look at Sidecar and Ambient Modes

---

## ⚙️ Setting Up the Environment for Istio

### 🎯 Goal:

Prepare your local machine to **install and run Istio** using Minikube, Kubectl, and Helm.

---

## 🧱 Prerequisites

| Tool         | Purpose                                    |
| ------------ | ------------------------------------------ |
| **Minikube** | Local Kubernetes cluster for testing & dev |
| **kubectl**  | CLI to interact with your K8s cluster      |
| **Helm**     | Package manager for Kubernetes             |

---

## 💻 System Requirements

- 🧠 **CPU**: Minimum 4 cores (Recommended: 6 cores)
- 💾 **Memory**: At least 8 GB RAM (Recommended: 7+ GB for cluster)
- 💽 **Disk**: 20 GB free
- ⚙️ **Kubernetes** version: 1.28 – 1.31

---

## 🛠️ Step-by-Step Tool Installation

### 1. **Install Minikube**

- ✅ Visit [Minikube Docs](https://minikube.sigs.k8s.io/docs/start/)
- 📦 On macOS? Use **Homebrew**:

  ```bash
  brew install minikube
  ```

- 🔍 Verify installation:

  ```bash
  minikube version
  ```

---

### 2. **Install kubectl**

- ✅ Visit [kubectl Docs](https://kubernetes.io/docs/tasks/tools/)
- 📦 For macOS:

  ```bash
  brew install kubectl
  ```

- 🔍 Verify:

  ```bash
  kubectl version --client
  ```

---

### 3. **Install Helm**

- ✅ Visit [Helm Docs](https://helm.sh/docs/intro/install/)
- 📦 For macOS:

  ```bash
  brew install helm
  ```

- 🔍 Verify:

  ```bash
  helm version
  ```

---

## 🚀 Start Your Local Kubernetes Cluster

### Run Minikube:

```bash
minikube start --profile=istio-demo --cpus=6 --memory=7168
```

- Creates a Minikube cluster named `istio-demo`
- Assigns 6 CPUs and \~7GB RAM
  _You can reduce resources if needed, but ensure Istio has enough to operate._

---

### 🔍 Confirm Cluster Is Running:

```bash
kubectl cluster-info
```

You should see:

- Control plane IP
- CoreDNS service status
  ✅ This confirms your cluster is ready!

---

## 🎉 Summary

By the end of this setup:

- ✅ **Minikube** is running locally
- ✅ You have **kubectl** and **Helm** ready
- ✅ Kubernetes cluster is live and verified

---

### ⏭️ Next Up:

We’ll **download Istio** and **install it using Helm in Ambient mode**.

---

## 📦 Installing Istio with Helm

### 🛠️ Installation Method

We’re using **Helm** — a reliable and flexible package manager for Kubernetes — to install **Istio in ambient mode**.

---

## 🧭 Pre-Installation Checklist

- ✅ Minikube up and running
- ✅ kubectl and Helm installed
- ✅ Kubernetes version between 1.28 – 1.31
- ✅ Environment-specific prerequisites reviewed (check [Istio Docs](https://istio.io/latest/docs/setup/platform-setup/))

---

## 🚀 Step-by-Step Installation

### 1. **Add Istio Helm Repository**

```bash
helm repo add istio https://istio-release.storage.googleapis.com/charts
helm repo update
```

- Adds the official Istio Helm chart repo.
- Fetches the latest versions.

---

### 2. **Download Istio CLI Tools (Optional but Recommended)**

```bash
curl -L https://istio.io/downloadIstio | sh -
cd istio-*
cd bin
export PATH=$PWD/bin:$PATH
```

- Gives you access to `istioctl` and sample configs.
- Make `istioctl` available globally.

---

### 3. **Install Istio Base**

```bash
helm install istio-base istio/base -n istio-system --create-namespace --set defaultRevision=default --wait
```

- Installs **CRDs** and sets up **RBAC permissions**.
- All Istio components will live in the `istio-system` namespace.

---

### 4. **Install Gateway API CRDs**

This will install Istiod If not found:

```bash
kubectl get crd gateways.gateway.networking.k8s.io &> /dev/null || kubectl apply -f https://github.com/kubernetes-sigs/gateway-api/releases/download/v1.0.0/standard-install.yaml

```

- Required for managing traffic via Istio Gateway.

---

### 5. **Install istiod (Control Plane)**

```bash
helm install istiod istio/istiod -n istio-system --set profile=ambient --wait
```

- `istiod` is the **brain** of the mesh — handles configuration, service discovery, policies.

---

### 6. **Install Istio CNI**

```bash
helm install istio-cni istio/cni -n istio-system --set profile=ambient --wait
```

- Sets up **CNI plugin** for ambient mode.
- Ensures smooth traffic redirection without sidecars.

---

### 7. **Install ztunnel (Data Plane for Ambient Mode)**

```bash
helm install ztunnel istio/ztunnel -n istio-system
```

- ztunnel manages secure traffic between pods.
- No sidecars needed — uses a DaemonSet.

---

### 8. **Install Ingress Gateway**

```bash
helm install istio-ingressgateway istio/gateway -n istio-ingress --create-namespace
```

- Enables **external access** to services in the mesh.

---

## 🧪 Verify Installation

```bash
helm list -n istio-system
kubectl get pods -n istio-system
```

You should see:

- `istiod`
- `ztunnel`
- `istio-cni`
- All in **Running** or **Completed** state

---

## ✅ Summary

You’ve successfully installed:

- 🧠 **Istio Control Plane** (`istiod`)
- 🔌 **CNI Plugin** and **ztunnel** for the ambient data plane
- 🌐 **Ingress Gateway** for exposing services

---

### ⏭️ Next Up:

We’ll **deploy a sample app** and **add it to the ambient mesh** to demonstrate Istio’s capabilities in action.

## 📚 Istio Bookinfo Sample Application

### 🔧 What is Bookinfo?

- A **mock e-commerce app** used to showcase **Istio features**.
- Composed of **multiple microservices**, each written in a **different language**, to simulate real-world environments.

### 📦 Microservice Architecture:

| Service       | Responsibility                                       |
| ------------- | ---------------------------------------------------- |
| `productpage` | Entry point; retrieves book info from other services |
| `details`     | Provides book description and author info            |
| `reviews`     | Displays customer reviews; calls `ratings`           |
| `ratings`     | Provides star ratings; called by `reviews`           |

---

### 🗂️ Kubernetes Resources (from `bookinfo.yaml`)

- **Services**: Route traffic to each microservice (e.g., `reviews` on port 9080).
- **Deployments**: Define how microservices are run, including multiple versions.
- **ServiceAccounts**: Assign pod identities to enable secure communication within the cluster.

---

### 🌐 Ingress Configuration (from `bookinfo-gateway.yaml`)

- **Gateway Resource**:

  - Defines how **external traffic** enters the **service mesh**.
  - Uses a **selector** to bind to the Istio Ingress Gateway.

- **VirtualService Resource**:

  - Manages **internal routing** once traffic enters the mesh.
  - Defines how traffic is directed to the appropriate microservice.

---

### 🛠️ Deployment Steps

1. **Create Namespace**:

   ```bash
   kubectl create namespace bookinfo
   ```

2. **Deploy Application**:

   ```bash
   kubectl apply -f k8s/bookinfo.yaml -n bookinfo
   ```

3. **Verify Pod Status**:

   ```bash
   kubectl get pods -n bookinfo
   ```

4. **Expose App via Ingress Gateway**:

   - Confirm the gateway:

     ```bash
     kubectl get svc istio-ingressgateway -n istio-ingress
     ```

   - If using **Minikube**, run tunnel in a new terminal:

     ```bash
     minikube tunnel
     ```

   - Recheck external IP:

     ```bash
     kubectl get svc istio-ingressgateway -n istio-ingress
     ```

5. **Apply Gateway + VirtualService**:

   ```bash
   kubectl apply -f k8s/bookinfo-gateway.yaml -n bookinfo
   ```

6. **Test Access**:

   - Curl:

     ```bash
     curl http://localhost/productpage
     ```

   - Or open in browser:

     ```
     http://localhost/productpage
     ```

> 🌀 You'll observe the `reviews` section randomly rotating between different versions (v1, v2). This demonstrates Istio's traffic distribution capabilities.

---

### 📈 Next Steps

- Add the application to the **service mesh**
- Generate traffic
- **Visualize and secure** communication with **Kiali**

### 🔐 **Add App to Ambient Mesh with Mutual TLS**

- Label namespace to join mesh:

  ```bash
  kubectl label namespace bookinfo istio.io/dataplane-mode=ambient
  ```

- ✅ No pod restarts required. mTLS is automatically enabled.

---

### 7. 📊 **Visualize Traffic with Prometheus + Kiali**

for we to visualize we need to Install Istio Observability Add-ons

```bash
mkdir -p istio-addons
curl -L https://raw.githubusercontent.com/istio/istio/release-1.25/samples/addons/prometheus.yaml -o istio-addons/prometheus.yaml
curl -L https://raw.githubusercontent.com/istio/istio/release-1.25/samples/addons/grafana.yaml -o istio-addons/grafana.yaml
curl -L https://raw.githubusercontent.com/istio/istio/release-1.25/samples/addons/kiali.yaml -o istio-addons/kiali.yaml
curl -L https://raw.githubusercontent.com/istio/istio/release-1.25/samples/addons/jaeger.yaml -o istio-addons/jaeger.yaml

kubectl apply -f k8s/istio-addons/ -n istio-system
```

To confirm pods

```bash
kubectl get svc -n istio-system
```

To open kiali dashboard:

```bash
istioctl dashboard kiali

#or get svc of kiali and portforward

kubectl get svc -n istio-system
kubectl port-forward svc/kiali -n istio-system 20001:20001

```

Open new terminal and simulate traffic :

```bash

for i in $(seq 1 100); do
curl -s http://localhost:productpage
done

```

now refresh kiali dashboard to see the traffic:

### 🔐 **Visualizing and Securing Traffic in Istio with Kiali and ztunnel (Ambient Mode)**

After deploying the **Bookinfo application** and configuring routing via the **Istio Ingress Gateway**, we can now visualize and secure traffic using **Kiali**.

#### 🔎 Traffic Graph in Kiali

- Navigate to the **Traffic Graph** section in Kiali.
- You'll see how the `productpage` receives traffic through the **Ingress Gateway**, then fans out requests to `reviews`, `details`, and `ratings`.
- This graph provides real-time visibility into service interactions and routing paths within the mesh.

#### 🔐 Confirming Mutual TLS (mTLS)

- In the Kiali UI, switch to the **Security** view.
- You'll notice **padlock icons** between services — this confirms **mutual TLS** is active.
- Click on the connections to verify: it should show **“mTLS Enabled.”**

#### 🔧 How Ambient Mode (ztunnel) Secures Traffic

- Istio **ztunnel** is the lightweight data plane component in Ambient Mode.
- It handles all **secure traffic** (L4 routing and encryption) **without sidecar proxies**.

To verify ztunnel activity:

### 🔒 6. **Verify Mutual TLS**

- In **Kiali**, navigate to:

  ```
  Graph > Click on an edge or service > Security tab
  ```

- Confirm padlocks (🔒) and **mTLS enabled** status.

---

### 🔎 7. **Inspect Traffic via zTunnel**

- View zTunnel logs:

  ```bash
  kubectl get pods -n istio-system
  stern ztunnel -n <z-tunnel-pod>
  ```

---

## 🧠 Key Concepts Highlighted

| Concept               | Explanation                                                                 |
| --------------------- | --------------------------------------------------------------------------- |
| **Ambient Mesh**      | Istio mode with sidecarless data plane (zTunnel) for simplified operations. |
| **mTLS (Mutual TLS)** | Encrypts service-to-service traffic inside the mesh.                        |
| **Kiali**             | Istio’s UI for visualizing mesh topology and real-time traffic.             |
| **zTunnel**           | Handles transparent, secure traffic routing without sidecars.               |

---

---

## 🔐 Verifying Mutual TLS (mTLS) in Istio Ambient Mesh

Once your workloads are part of the mesh, it’s crucial to **validate that mTLS is actively securing communication**. Below are **four ways to confirm** it:

---

### ✅ **1. Use `istioctl ztunnel-config workloads`**

This command confirms that **HBONE** (HTTP/2-based overlay network protocol used in ambient mesh with mTLS) is active.

```bash
istioctl ztunnel-config workloads
```

- Look for the `HBONE` protocol listed under workloads in the `bookinfo` namespace.
- ⚠️ **Note**: Seeing `HBONE` indicates secure routing is possible, but it does **not block plaintext traffic**. To enforce strict encryption, you must configure:

  ```yaml
  PeerAuthentication:
    mtls:
      mode: STRICT
  ```

---

### 📊 **2. Check Prometheus Metrics**

**Prometheus Metric**: `istio_tcp_connections_opened_total`

- Open **Prometheus Dashboard**
- Go to **Graph** section.
- Enter the following query:

  ```text
  istio_tcp_connections_opened_total
  ```

- Click **Execute**.
- Look for the label:

  ```
  connection_security_policy = "mutual_tls"
  ```

✅ This confirms that mTLS is actively used for open TCP connections.

---

### 📈 **3. Inspect the Kiali Dashboard**

1. Open Kiali:

   ```bash
   istioctl dashboard kiali
   ```

2. Go to **Traffic Graph**.
3. Make sure you’re generating traffic:

   ```bash
   while true; do curl -s http://localhost/productpage > /dev/null; sleep 1; done
   ```

4. **Look for 🔒 padlocks between services**.
5. Click on a connection line → go to **Security** tab:

   - Confirm **mTLS Enabled**.
   - Under **Principals**, you’ll see **SPIFFE IDs**, e.g.:

     ```
     spiffe://cluster.local/ns/bookinfo/sa/productpage
     ```

ℹ️ **SPIFFE ID** is a unique identity (like a digital passport) used by Istio to securely authenticate services.

---

### 📋 **4. Check Logs in the `ztunnel` Pod**

1. Get the zTunnel pod:

   ```bash
   kubectl get pods -n istio-system | grep ztunnel
   ```

2. View logs using `stern` or `kubectl logs`:

   ```bash
   stern ztunnel -n istio-system
   # or
   kubectl logs <ztunnel-pod-name> -n istio-system
   ```

3. In logs, look for:

   - `src.identity`: Source SPIFFE ID
   - `dst.identity`: Destination SPIFFE ID

✅ This confirms **secure identity-based routing using mTLS**.

---

## 🧠 Summary Table

| Method                     | Tool Used     | What to Look For                              |
| -------------------------- | ------------- | --------------------------------------------- |
| `ztunnel-config workloads` | `istioctl`    | `HBONE` protocol listed                       |
| Prometheus Metric          | Prometheus UI | `connection_security_policy=mutual_tls`       |
| Kiali Dashboard            | Kiali         | 🔒 padlocks + SPIFFE IDs under Security       |
| zTunnel Logs               | stern/logs    | `src.identity` and `dst.identity` with SPIFFE |

---

######

######

######

---

## 🚦 **How Istio Ensures Smooth Traffic Flow in Microservices**

Modern microservice architectures involve **dozens or hundreds of services** talking to each other. Without proper coordination, this can lead to **delays, bottlenecks, or outright failure**. That’s where **Istio** comes in — acting like a **traffic controller** for your app’s internal communication.

---

### 🧭 **Istio = Smart Traffic Controller**

Think of your microservices as cars in a busy city. Just like traffic lights and signs prevent chaos, **Istio intelligently directs service traffic**, ensuring:

- ✅ Secure communication
- ✅ Balanced traffic distribution
- ✅ Resilience to failure
- ✅ Controlled feature rollouts

---

### 🛣️ **How Istio Directs Traffic**

1. **Service Registry**:

   - Istio automatically discovers services via Kubernetes’ internal registry.
   - For **external services**, you can define **ServiceEntry** resources.

2. **Ztunnel (L4 traffic handler)**:

   - Runs on **every Kubernetes node**
   - Handles **Layer 4 (TCP)** traffic
   - Encrypts and forwards requests securely inside the mesh.

3. **Waypoint Proxy (L7 traffic handler)**:

   - Manages **Layer 7 (HTTP)** traffic for advanced logic:

     - Load balancing
     - Request retries
     - Circuit breaking
     - Fault injection
     - Header-based routing

4. **Istio Gateways**:

   - Handle **incoming/outgoing traffic** from outside your mesh.

---

### 🧰 **Key Traffic Management Features in Istio**

| Feature                | Purpose                                                                                              |
| ---------------------- | ---------------------------------------------------------------------------------------------------- |
| **VirtualService**     | Defines **how traffic is routed** to a service (e.g., canary, A/B tests).                            |
| **DestinationRule**    | Sets **policies** like load balancing and connection settings **after traffic reaches the service**. |
| **Fault Injection**    | Simulates service failures to test **resilience** and fallback behavior.                             |
| **Retries & Timeouts** | Automatically retries failed requests or times out after delays.                                     |
| **Circuit Breaking**   | Prevents **overloading** a service by temporarily blocking traffic when it's unhealthy.              |
| **A/B Testing**        | Sends new features to a **subset of users** before full rollout.                                     |

---

### 📌 In Summary

Istio ensures **smooth, secure, and intelligent traffic flow** through:

- Auto-discovery via service registry
- Encrypted routing with `ztunnel`
- Advanced traffic logic with **waypoint proxies**
- Policies defined through custom Istio resources

In the upcoming videos or docs, you’ll get hands-on with:

- Routing rules
- Failover strategies
- Load balancing setups
- Resilience testing through fault injection and circuit breaking

---

---

## 🚦 **Istio Virtual Services: Smart Routing for Microservices**

### 🧠 **What Is a Virtual Service in Istio?**

A **VirtualService** in Istio lets you **define how requests are routed** to a service — like a **traffic controller** for your app's network.

Think of your app like a **busy city** and virtual services as the **intelligent, programmable map** telling each request where to go — dynamically, and with rules you define.

---

### 🎯 **Why Virtual Services Are Powerful**

Virtual services allow you to create **custom traffic routing rules** based on:

| Routing Criteria | Example Use Case                                    |
| ---------------- | --------------------------------------------------- |
| **HTTP headers** | Route based on a user's identity (`end-user: JSON`) |
| **Request path** | Route `/v2/orders` to a specific version            |
| **HTTP methods** | Send `GET` and `POST` to different destinations     |
| **Port numbers** | Target traffic through specific ports               |

---

### 📄 **Example VirtualService YAML**

Here’s a simple breakdown of a virtual service YAML file used in the BookInfo app:

```yaml
apiVersion: networking.istio.io/v1beta1
kind: VirtualService
metadata:
  name: reviews-route
spec:
  hosts:
    - reviews
  http:
    - match:
        - headers:
            end-user:
              exact: JSON
      route:
        - destination:
            host: reviews
            subset: v2
    - route:
        - destination:
            host: reviews
            subset: v3
```

🧩 **What's `subset`?**
It refers to a **specific version** of the service (like `v2`, `v3`) — defined in the corresponding `DestinationRule`.

---

### ⚖️ **Weighted Routing (A/B Testing or Canary Releases)**

You can split traffic between versions **gradually**:

```yaml
route:
  - destination:
      host: reviews
      subset: v1
    weight: 75
  - destination:
      host: reviews
      subset: v2
    weight: 25
```

🔧 Total weight must always equal **100%**.

---

### 🛠️ **Routing by URL Prefix**

You can match and route traffic based on the URL path:

```yaml
match:
  - uri:
      prefix: '/content/reviews'
```

This allows fine-grained control over what endpoints route to which services.

---

### 💡 **Pro Tip for Host Naming**

- `host: reviews` → Istio auto-expands this to `reviews.<namespace>.svc.cluster.local`
- ✅ **Best practice**: Use the full FQDN (`reviews.bookinfo.svc.cluster.local`) to **avoid namespace-related issues**.

---

### 🔄 **What Happens After Routing?**

Once traffic reaches its destination, **DestinationRules** take over to:

- Apply **load balancing**
- Handle **retries and timeouts**
- Perform **circuit breaking**

> These will be covered in the next section.

---

---

## 🛣️ **Istio Destination Rules: Managing Traffic After It Arrives**

### 🚥 **What Are Destination Rules?**

If **VirtualServices** guide traffic to the correct **destination**, then **DestinationRules** define **what happens to that traffic when it gets there** — like **traffic laws inside a city**.

---

### 🔄 **Why Are Destination Rules Important?**

They:

- Define **subsets** (e.g., versioned deployments like `v1`, `v2`) based on pod labels
- Apply **traffic policies** like load balancing, TLS, and circuit breaking

---

### 🧩 **How Subsets Work (Versioning Magic)**

1. **Pods** in your Kubernetes `Deployment` have labels:

   ```yaml
   labels:
     app: reviews
     version: v2
   ```

2. **DestinationRule** defines subsets using those labels:

   ```yaml
   subsets:
     - name: v1
       labels:
         version: v1
     - name: v2
       labels:
         version: v2
   ```

3. Then, **VirtualService** can route traffic like:

   ```yaml
   route:
     - destination:
         host: reviews
         subset: v1
   ```

✅ This allows Istio to route traffic **based on specific versions** of your service.

---

### ⚙️ **Traffic Policies in Destination Rules**

Destination rules allow you to define how traffic behaves once it reaches the destination via:

| Feature              | Description                                                               |
| -------------------- | ------------------------------------------------------------------------- |
| **Load Balancing**   | Controls how requests are distributed among pods                          |
| **TLS Policies**     | Secures traffic between services using mTLS                               |
| **Circuit Breaking** | Prevents services from being overwhelmed by high traffic or failure rates |

---

### ⚖️ **Load Balancing Strategies in Istio**

| Strategy                    | Description                                                                 |
| --------------------------- | --------------------------------------------------------------------------- |
| **Least Request** (default) | Sends traffic to the pod with the **fewest active requests**                |
| **Random**                  | Sends traffic to a **random** pod                                           |
| **Round Robin**             | Cycles through all pods **in order**                                        |
| **Weighted**                | Manually control traffic percentage to each version (used in A/B or canary) |

---

### 📄 **Example DestinationRule with Subsets and Load Balancing**

```yaml
apiVersion: networking.istio.io/v1beta1
kind: DestinationRule
metadata:
  name: ratings-destination
spec:
  host: ratings
  subsets:
    - name: v1
      labels:
        version: v1
    - name: v3
      labels:
        version: v3
      trafficPolicy:
        loadBalancer:
          simple: ROUND_ROBIN
  trafficPolicy:
    loadBalancer:
      simple: LEAST_REQUEST
```

### 🔍 Explanation:

- All traffic to `ratings` defaults to **least request**.
- Traffic to **subset `v3`** uses **round robin** instead.

---

### 🔐 **Bonus: Add TLS and Circuit Breaking**

You can enhance security and resilience like so:

```yaml
trafficPolicy:
  tls:
    mode: ISTIO_MUTUAL
  connectionPool:
    http:
      http1MaxPendingRequests: 100
      maxRequestsPerConnection: 10
  outlierDetection:
    consecutiveErrors: 5
    interval: 10s
    baseEjectionTime: 30s
```

---

### ✅ **Recap**

- **DestinationRules** define **how traffic behaves** once it hits a service
- They enable **versioned routing**, **secure connections**, and **resilient load balancing**
- Complement **VirtualServices** which handle **how traffic gets to the service**

---

######

######

######

---

### 🔹 **Ambient Mode & Waypoint Proxies in Istio**

- **Ambient Mode**: An Istio data plane mode that **eliminates the need for sidecars** per pod.
- **Waypoint Proxies**:

  - Envoy-based Layer 7 proxies used in **ambient mode**.
  - Handle traffic for **multiple services**, not per service.
  - Enable full **Layer 7 features**: HTTP routing, load balancing, fault injection.
  - Deployed only when Layer 7 features are needed (after `ztunnel` handles Layer 4).

#### ✅ **Steps to Deploy Waypoint Proxy**

1. **Check namespace label**:

   ```bash
   kubectl get ns -L istio.io/dataplane-mode
   ```

   Make sure it is labeled `ambient`.

2. **Review and apply `waypoint.yaml`**:

   - Uses `gatewayClassName: istio-waypoint`.
   - Label: `istio.io/waypoint-for: service`.
   - Listener port: `15008`.

   ```bash
   kubectl apply -f k8s/waypoint.yaml -n bookinfo
   ```

3. **Verify the gateway creation**:

   ```bash
   kubectl get gateway -n bookinfo
   ```

   Check that `Programmed` is `True`.

4. **Label namespace to use the waypoint**:

   ```bash
   kubectl label ns bookinfo istio.io/use-waypoint=waypoint
   ```

---

### 🔹 **Traffic Routing with VirtualService & DestinationRule**

#### 🧪 Round-Robin by Default

- Istio routes requests across different versions (v1, v2, v3) of a service using round-robin if no routing rules are defined.

#### 🎯 **Routing All Traffic to v1**

1. **DestinationRule** defines subsets based on pod labels:

   ```yaml
   subsets:
     - name: v1
       labels:
         version: v1
     - name: v2
       labels:
         version: v2
     - name: v3
       labels:
         version: v3
   ```

2. **VirtualService** routes traffic to subset v1:

   ```yaml
   route:
     - destination:
         host: reviews
         subset: v1
   ```

3. **Apply both configs**:

   ```bash
   kubectl apply -f k8s/destination-rule.yaml -n bookinfo
   kubectl apply -f k8s/virtual-service-all-v1.yaml -n bookinfo
   ```

4. **Validate in browser** or via **Kiali** (`localhost:20001/kiali`): only version 1 of reviews shows.

---

### 🔹 **User-Based Traffic Routing**

#### 🧍 Jasmine sees v2, others see v1

- **Header-based routing using `end-user` HTTP header**.

- **VirtualService logic**:

  ```yaml
  - match:
      - headers:
          end-user:
            exact: jasmine
    route:
      - destination:
          host: reviews
          subset: v2
  - route:
      - destination:
          host: reviews
          subset: v1
  ```

- Apply config:

  ```bash
  kubectl apply -f k8s/virtual-service-reviews-v2-user.yaml -n bookinfo

  ### to confirm
  kubectl get virtualservices reviews -o yaml
  ```

- **Test** by logging in as different users:

  - `jasmine` → sees **reviews v2** (with star ratings).
  - Others (e.g. `dave`) → see **reviews v1**.

---

---

### 🧭 **What is Traffic Shifting in Istio?**

Traffic shifting lets you **gradually direct traffic** between different versions of a microservice. This is helpful for **canary releases** or **progressive rollouts**.

---

### 🛠️ **Core Concept: Weighted Routing**

Istio’s **VirtualService** uses **weights** to distribute traffic between service versions.

Example:

```yaml
http:
  - route:
      - destination:
          host: reviews
          subset: v1
        weight: 50
      - destination:
          host: reviews
          subset: v3
        weight: 50
```

- Weights must sum to **100**.

---

### 📁 **Files Used**

1. **`virtual-service-all-v1.yaml`**

   - Routes 100% traffic to version 1 of all services.

2. **`virtual-service-reviews-50-v3.yaml`**

   - Routes 50% to `reviews:v1`, 50% to `reviews:v3`.

3. **`virtual-service-reviews-v3.yaml`**

   - Routes 100% to `reviews:v3` (no weights needed).

---

### 🧪 **Steps Followed**

1. **Initial Setup:**

   ```bash
   kubectl apply -f k8s/virtual-service-all-v1.yaml
   ```

   - Confirms all traffic goes to `reviews:v1`.

2. **Start Traffic Shifting (50/50):**

   ```bash
   kubectl apply -f k8s/virtual-service-reviews-50-v3.yaml
   ```

   - Refreshing the app alternates between `v1` and `v3` views.

3. **Confirm in Kiali Dashboard:**

   - Generate traffic,

   ```bash
   for i in $(seq 1 100); do
   curl -s http://localhost:productpage
   done

   ```

   then go to service in kiali, reviews Shows traffic split (e.g., \~50% to each).

4. **Final Shift to 100% v3:**

   ```bash
   kubectl apply -f k8s/virtual-service-reviews-v3.yaml
   ```

   - All traffic now goes to `reviews:v3`.

---

### ✅ **Outcome**

- **Progressive rollout** complete.
- Ensures stable deployment without downtime or risk to users.

---

---

### 🧪 Fault Injection with Istio: Simulate Failures Before They Happen

### 💥 What is Fault Injection?

Fault injection is used to **simulate real-world failures** like:

- High latency (delays)
- Service crashes (HTTP 500s)
- Network issues

This helps **test the resilience** of your microservices and ensure graceful error handling.

---

firstly redirect all back to v1

```bash
 kubectl apply -f k8s/virtual-service-all-v1.yaml -n bookinfo

  kubectl apply -f k8s/virtual-service-all-v2.yaml -n bookinfo

```

### 🔁 Phase 1: **Inject Delay (15s) for Jasmine**

You simulate a **slow backend call** to the ratings service.

#### 🧠 Key Concepts:

- **VirtualService** resource
- `http.fault.delay.fixedDelay: 15s`
- `match.headers.end-user.exact: "jasmine"`

📁 Sample YAML:

```bash
 kubectl apply -f k8s/vs-delay-injection.yaml -n bookinfo
```

⏱ Result: Jasmine’s requests time out (`>6s`) while others are fine.

---

### ❌ Phase 2: **Simulate Failure (HTTP 500) for Jasmine**

You configure a virtual service to **abort requests**.

#### 🧠 Key Concepts:

- `http.fault.abort.httpStatus: 500`
- Again matched only for Jasmine

📁 Sample YAML:

```bash
 kubectl apply -f k8s/vs-abort-injection.yaml -n bookinfo
```

🔍 Result: Jasmine sees an error like:

> `Ratings service is currently unavailable`

---

#### 2️⃣ Simulated Service Failure (Abort Fault)

- We then configured Istio to return a **500 Internal Server Error** for requests from Jasmine to the `ratings` service.
- Used the `abort` fault injection rule.
- **Result:** Jasmine saw a "ratings service unavailable" message. Other users continued to get normal responses.

🎯 **Why it matters:**
Fault injection helps detect cascading failures, test timeouts, and identify how resilient your services really are—**before issues hit production**.

---

---

### ⏱️ Timeouts & 🔁 Retries in Istio: Making Microservices More Resilient

## ⏱️ Timeouts in Istio

**Purpose:**
Prevent services from waiting indefinitely for responses from other services.

```bash
kns bookinfo
 kubectl apply -f k8s/review-02.yaml
kubectl apply -f k8s/virtual-service-all-v2.yaml

```

```bash
 kubectl apply -f k8s/vs-rating-details-delay.yaml
```

- Added a **2-second delay** to the rating and details services.

```bash
 kubectl apply -f k8s/vs-reviews-timeout.yaml
```

- Set a **0.5-second timeout** on the reviews service.
- Result: Requests timeout and users see `"Error fetching product reviews"`.

### 💡 Why This Matters:

- Timeout setting makes the system **fail fast**, improving responsiveness.
- Default behavior: Istio has **no timeouts by default**, so services might hang if another is slow.

---

## 🔁 Retries in Istio

**Purpose:**
Retry failed requests automatically to improve success rates in case of **temporary issues** (e.g., network glitches).

### ✅ Example Configuration:

- Retry failed calls to the rating service **up to 3 times**, within a 2-second timeout per attempt.
- After applying the retry config:

  - Errors disappeared.
  - App recovered and loaded correctly.
  - Kiali dashboard shows green (healthy communication).

```bash
 kubectl apply -f k8s/vs-ratings-retry.yaml
```

### ⚠️ Best Practices:

- Avoid aggressive retries. Too many retries can **overload** services and worsen failures.
- Balance is key: combine with **timeouts** and **circuit breakers**.

---

## Summary Table:

| Feature         | What It Does                                       | When to Use                          |
| --------------- | -------------------------------------------------- | ------------------------------------ |
| Fault Injection | Simulate failures or slow responses                | Test resilience, uncover hidden bugs |
| Timeout         | Limit how long a service waits for another service | Prevent hanging requests             |
| Retry           | Automatically re-send failed requests              | Handle transient failures            |

---

#### ⏱️ Timeouts: Don’t Wait Forever

In our **BookInfo** app:

- The `productpage` service calls the `reviews` service.
- We introduced a **2-second delay** to the downstream `ratings` service.
- Then, we set a **0.5-second timeout** on the `reviews` service using Istio.

📉 **Result:** The `reviews` service exceeded the timeout due to the downstream delay, causing the product page to fail fetching reviews.

🔍 **Key insight:** By setting a timeout, we prevent services from hanging indefinitely and surface performance issues early.

#### 🔁 Retries: Handle Temporary Glitches

Timeouts prevent waiting, but what if the failure is **temporary**?

We added a retry policy to the `ratings` service:

- Istio retried failed calls up to **3 times** within a **2-second window**.
- After applying the retry config, the BookInfo app resumed normal operation despite the delay.

📈 **Result:** System recovered from transient errors without manual intervention.

#### 📊 Observability

We used **Kiali** to visualize:

- Broken communication before retries were applied (red edges).
- Healthy communication paths after retry logic was introduced (green edges).

---

### 🚀 Takeaways:

- **Timeouts** help avoid cascading failures by limiting wait times.
- **Retries** help overcome temporary issues, like network blips.
- Combined, they make your services **faster**, **smarter**, and more **resilient**.

Next up: when even retries aren’t enough — **Circuit Breaking** 🧯.

---

---

### 💡 🧯 Circuit Breaking in Istio

## 🔎 Overview

Circuit breaking in Istio prevents a failing or overloaded service from affecting the entire system. When a service becomes unreliable (e.g., slow, error-prone), Istio can stop sending traffic to it temporarily — giving it a chance to recover while keeping your system stable.

This is done using a **DestinationRule** that configures connection limits, request limits, and outlier detection.

---

## 📁 Files Used

1. **`deploy_httpbin.yaml`** – Deploys the `httpbin` sample service
2. **`fortio_client.yaml`** – Deploys Fortio, a client to simulate traffic and load
3. **`destinationrule_circuitbreaker.yaml`** – Defines the circuit breaking configuration for `httpbin`

---

## 🛠️ YAML Configuration Breakdown

### `destinationrule_circuitbreaker.yaml`

```yaml
apiVersion: networking.istio.io/v1
kind: DestinationRule
metadata:
  name: httpbin
spec:
  host: httpbin
  trafficPolicy:
    connectionPool:
      tcp:
        maxConnections: 1
      http:
        http1MaxPendingRequests: 1
        maxRequestsPerConnection: 1
    outlierDetection:
      consecutive5xxErrors: 1
      interval: 1s
      baseEjectionTime: 3m
      maxEjectionPercent: 100
```

🔍 **Key Settings**:

- `maxConnections`: Allows only **1 TCP connection**
- `maxRequestsPerConnection`: Restricts to **1 HTTP request per connection**
- `outlierDetection`:

  - Ejects instance after **1 consecutive 5xx error**
  - Keeps it ejected for **3 minutes**
  - Monitors errors every **1 second**

---

## 🚀 Step-by-Step Deployment

### Step 1: Deploy `httpbin` Service

```bash
kubectl apply -f deploy_httpbin.yaml -n bookinfo
```

Creates:

- Deployment
- Service
- Service Account

### Step 2: Deploy Fortio Client

```bash
kubectl apply -f fortio_client.yaml -n bookinfo
```

Used for generating load and testing the circuit breaker behavior.

### Step 3: Apply DestinationRule with Circuit Breaker Config

```bash
kubectl apply -f destinationrule_circuitbreaker.yaml -n bookinfo
```

✅ Confirm the rule:

```bash
kubectl get destinationrule httpbin -n bookinfo -o yaml
```

---

## 🧪 Load Testing with Fortio

### Get the Fortio Pod Name

```bash
export fortio_pod=$(kubectl get pod -n bookinfo -l app=fortio -o jsonpath='{.items[0].metadata.name}')
```

### Send a Simple Request

```bash
kubectl exec -n bookinfo $fortio_pod -c fortio -- curl http://httpbin:8000/get
```

Returns `200 OK` — service is running.

---

### Simulate Load

#### 2 Connections, 20 Requests

```bash
kubectl exec -n bookinfo $fortio_pod -c fortio -- fortio load -c 2 -n 20 http://httpbin:8000/get
```

Should still return `200 OK` — service is healthy.

#### Repeat to Trigger Circuit Breaker

```bash
kubectl exec -n bookinfo $fortio_pod -c fortio -- fortio load -c 2 -n 20 http://httpbin:8000/get
```

Expect to start seeing some `503` responses.

#### Increase Load: 3 Connections, 30 Requests

```bash
kubectl exec -n bookinfo $fortio_pod -c fortio -- fortio load -c 3 -n 30 http://httpbin:8000/get
```

You should now see a **higher error rate** (\~43% `503` errors) — circuit breaker is in action, ejecting the service.

---

## 🧠 Key Takeaways

- Istio's **DestinationRule** is used to enforce circuit breaking logic.
- Circuit breaking limits overload by:

  - Capping connections and requests
  - Automatically removing (ejecting) unhealthy instances

- This improves **resilience**, **recovery**, and **overall system stability**.

---

---

---

### 🔐 **Why Security Matters in Microservices**

In microservices architectures like the BookInfo app (product page, reviews, details services), traffic between services can be intercepted or tampered with by attackers. For example, a request from the product page to the reviews service could be modified, or sensitive data might be exposed.

---

### 🛡️ **How Istio Secures Your Microservices**

1. **Encryption with Mutual TLS (mTLS):**

   - Istio **automatically encrypts traffic between services** using mutual TLS.
   - This ensures that requests (e.g., product page to details) are **confidential and tamper-proof**. No one in between can spy on or alter the data.

2. **Access Control:**

   - Istio enforces **strict service-to-service authentication**.
   - For example, the product page can only communicate with authorized services like reviews or details.
   - It prevents rogue or unauthorized services from masquerading and accessing your app’s services.

3. **Service Identity and Auditing:**

   - Istio assigns a **unique identity to each service** (like a strong digital certificate).
   - This identity is used to **verify requests and maintain audit logs** — so you know who accessed what, when, and how.
   - For example, if reviews calls ratings, Istio validates the request and logs the interaction for monitoring and security audits.

---

### 🔜 **Upcoming Topics**

The video series will go deeper into:

- Authentication (verifying identities)
- Authorization (permissions control)
- Certificate management (handling keys for encryption)

---

### Summary

Istio’s security features **protect your microservices communication** by encrypting traffic, verifying identities, enforcing access policies, and enabling traceability — all essential for a secure, resilient application.

---

---

## 🔐 Authentication in Istio Service Mesh

### What is Authentication?

Authentication asks the question: **"Are you really who you say you are?"**
In a service mesh, this ensures only trusted services communicate with each other, preventing rogue or unauthorized services from joining the conversation.

---

### Two Main Types of Authentication in Istio Ambient Mesh

1. **Peer Authentication**

   - Ensures **mutual trust between services** sending and receiving requests.
   - Works like a handshake using **mutual TLS (mTLS)** — both sides verify each other's identities before communicating.
   - Example: When the product page service talks to the reviews service, both verify each other’s identity with mTLS.

2. **Request Authentication**

   - Verifies **who is making the request** (the client identity).
   - Uses **JWT (JSON Web Tokens)** found in HTTP headers (typically under `Authorization: Bearer <token>`).
   - Istio checks the JWT against trusted identity providers like **Keycloak** or **Google Auth**.
   - Requests with valid tokens are allowed; invalid ones are rejected.

---

### mTLS Modes in Istio

- **Permissive Mode (default)**

  - Accepts **both encrypted (mTLS) and non-encrypted traffic**.
  - Useful when migrating services gradually to the mesh or when you don't want to block traffic immediately.

- **Strict Mode**

  - Allows **only encrypted mTLS traffic**.
  - This is the most secure mode and ensures **all service-to-service communication is encrypted** and verified.

---

---

# 🔐 Enforcing Peer Authentication in Istio with mTLS

## 🎯 Objective

Demonstrate how **Istio PeerAuthentication** in `STRICT` mode blocks non-mTLS traffic — ensuring that only **encrypted, secure service-to-service communication** is allowed.

---

## 🧪 Step-by-Step Walkthrough

### ✅ 1. Confirm BookInfo Pods Are Running

```bash
kubectl get pods -n bookinfo
```

Ensure that the **BookInfo** sample app (e.g., `productpage`, `reviews`, etc.) is up and running.

---

### 📦 2. Deploy a Curl Test Client in a New Namespace (`bar`)

```bash
kubectl create ns bar
kubectl apply -f curl.yaml -n bar
```

> This deploys a minimal curl container in the `bar` namespace to simulate cross-namespace traffic.

You can verify:

```bash
kubectl get pods -n bar
```

---

### 📡 3. Send a Request (Without mTLS) from `bar` to BookInfo

```bash
kubectl exec -n bar -it $(kubectl get pod -n bar -l app=curl -o jsonpath='{.items[0].metadata.name}') \
-- curl -s -o /dev/null -w "%{http_code}\n" http://productpage.bookinfo:9080
```

✅ **Expected result:**
You should see `200 OK` — this confirms that communication across namespaces **without mTLS** works by default.

---

### 🔐 4. Apply Peer Authentication Policy (mTLS STRICT) to `bookinfo`

```bash
kubectl apply -f peerAuthentication.yaml
```

**`peerAuthentication.yaml`:**

```yaml
apiVersion: security.istio.io/v1
kind: PeerAuthentication
metadata:
  name: bookinfo-peer-auth
  namespace: bookinfo
spec:
  mtls:
    mode: STRICT
```

🧠 This policy **enforces mTLS strictly** — meaning BookInfo services will **reject all plaintext traffic**, including from other namespaces like `bar`.

---

### ❌ 5. Re-run the Curl Request (Now It Fails)

```bash
kubectl exec -n bar -it $(kubectl get pod -n bar -l app=curl -o jsonpath='{.items[0].metadata.name}') \
-- curl -s -o /dev/null -w "%{http_code}\n" http://productpage.bookinfo:9080
```

🚫 **Expected result:**
The request fails with:

```
curl: (56) Recv failure: Connection reset by peer
command terminated with exit code 56
```

🔎 Explanation:

- The `bar` namespace does **not inject Istio sidecar proxies**, so its traffic is not mTLS-encrypted.
- The BookInfo services **reject the request** due to the `STRICT` mTLS mode.

---

## 🌐 Optional: Apply Cluster-Wide Peer Authentication

To **enforce mTLS across the entire mesh**, apply this in the `istio-system` namespace:

```yaml
apiVersion: security.istio.io/v1
kind: PeerAuthentication
metadata:
  name: default
  namespace: istio-system
spec:
  mtls:
    mode: STRICT
```

```bash
kubectl apply -f peerAuthentication-clusterwide.yaml
```

This ensures **all traffic** between services — across **all namespaces** — must use mTLS.

---

## 📁 Supporting Files

### `curl.yaml`

Minimal curl client to simulate cross-namespace requests:

```yaml
apiVersion: v1
kind: ServiceAccount
metadata:
  name: curl
---
apiVersion: v1
kind: Service
metadata:
  name: curl
  labels:
    app: curl
    service: curl
spec:
  ports:
    - port: 80
      name: http
  selector:
    app: curl
---
apiVersion: apps/v1
kind: Deployment
metadata:
  name: curl
spec:
  replicas: 1
  selector:
    matchLabels:
      app: curl
  template:
    metadata:
      labels:
        app: curl
    spec:
      terminationGracePeriodSeconds: 0
      serviceAccountName: curl
      containers:
        - name: curl
          image: curlimages/curl
          command: ['/bin/sleep', 'infinity']
          imagePullPolicy: IfNotPresent
```

---

## ✅ Summary

| Scenario                            | Result    | Why                               |
| ----------------------------------- | --------- | --------------------------------- |
| Curl request without mTLS (default) | ✅ 200 OK | No restrictions in place          |
| After applying mTLS STRICT policy   | ❌ 56     | Plaintext traffic is rejected     |
| Enable mTLS in `bar` namespace      | ✅        | If Istio sidecar is injected      |
| Cluster-wide STRICT mode            | ✅/❌     | Enforces mesh-wide secure traffic |

---

### Summary

- Authentication in Istio ensures **only trusted, verified services communicate** using mTLS and JWT validation.
- **Peer Authentication** handles service-to-service identity verification (mTLS handshake).
- **Request Authentication** validates client identities via JWT tokens.
- You can configure Istio to start with permissive mode and migrate gradually to strict mode enforcing full encryption.
- Applying these policies protects your mesh from unauthorized or insecure traffic, greatly increasing security posture.

---

---

## 🔐 Authorization in Istio Service Mesh

### What is Authorization?

Authorization answers the question:
**"What actions or services are allowed once authenticated?"**
After confirming identities (authentication), authorization determines **what each service is permitted to do.**

---

### Use Case Example: BookInfo Application

- The **product page service** wants to call the **review service**.
- We want to **restrict product page so it can only make GET requests** to reviews, preventing any harmful operations like POST or DELETE.

Istio allows you to define **authorization policies** that specify who can call what, and which HTTP methods they are allowed to use.

---

### Layer 4 vs Layer 7 Authorization Policies

- **Layer 4 Authorization (Network Level):**
  Controls which clients (based on service accounts or IPs) can communicate with specific services or workloads.
  Example: Allow only requests from the Istio Ingress Gateway to the product page service.

- **Layer 7 Authorization (Application Level):**
  Controls **HTTP methods, paths, headers, etc.** for fine-grained access control.
  Example: Allow only GET requests from a specific client namespace or service account.

---

---

## 🔐 Walkthrough: Implementing Istio Authorization Policies

In this walkthrough, we’ll secure access to the `productpage` service in the **Bookinfo application** using **Istio Authorization Policies**, implementing both **Layer 4 (L4)** and **Layer 7 (L7)** controls.

---

### ✅ Step 1: Layer 4 (L4) Authorization Policy

#### 🎯 Objective:

Restrict **any access** to the `productpage` pods **unless** it's from the **Istio Ingress Gateway's service account**.

#### 🛠️ Configuration:

```yaml
apiVersion: security.istio.io/v1
kind: AuthorizationPolicy
metadata:
  name: productpage-viewer
  namespace: bookinfo
spec:
  selector:
    matchLabels:
      app: productpage
  action: ALLOW
  rules:
    - from:
        - source:
            principals:
              - cluster.local/ns/istio-ingress/sa/istio-ingressgateway
```

```bash
kubectl apply f k8s/L4-productpage.yaml
kubectl get pods -n bar
kubectl exec deploy/curl -n bar --curl "http://productpage.bookinfo:9080/productpage"
```

#### 🔍 Expected Behavior:

- ✅ Access via browser or through the Ingress Gateway works as expected.
- ❌ Access from unauthorized sources (e.g., a `curl` pod in the `bar` namespace) is **denied**.

#### 📦 Test Results:

- **`curl` from unauthorized pod** → ❌ Access Denied
- **Browser access via Ingress** → ✅ Access Granted

---

### ✅ Step 2: Layer 7 (L7) Authorization Policy

> 💡 L7 policies require **Envoy Waypoint Proxy** to enforce HTTP-level rules (e.g., allowed HTTP methods).

#### 🎯 Objective:

Allow **only `GET` requests** from a specific workload identity (i.e., `curl` pod in `bar` namespace).

#### 🛠️ Configuration:

```yaml
apiVersion: security.istio.io/v1
kind: AuthorizationPolicy
metadata:
  name: productpage-viewer
  namespace: bookinfo
spec:
  targetRefs:
    - kind: Service
      group: ''
      name: productpage
  action: ALLOW
  rules:
    - from:
        - source:
            principals:
              - cluster.local/ns/bar/sa/curl
      to:
        - operation:
            methods: ['GET']
```

```bash
kubectl get gateway  -n bookInfo
kubectl apply f k8s/L7-product-page.yaml
kubectl get pods -n bar
```

#### 🔍 Expected Behavior:

- ✅ `GET` from `curl` pod (namespace `bar`) → **Allowed**
- ❌ `DELETE` or other HTTP methods → **Denied**
- ❌ Requests from other pods (e.g., `reviews`) → **Denied**

#### 📦 Test Results:

- **`curl -X DELETE` from curl pod** → ❌ `Method Not Allowed`
- **`curl -X GET` from curl pod** → ✅ Success
- **Access from reviews pod** → ❌ Access Denied

---

### 📌 Notes:

- **Waypoint Proxy Check**: Before applying L7 policies, verify that the **Waypoint Proxy** is running and programmed (`status.programmed: true`).
- **Policy Scoping**: L4 policies operate at the TCP level (before HTTP parsing), while L7 policies enforce fine-grained controls like HTTP verbs.

---

### 🧠 Summary:

- 🧱 L4 policy secured `productpage` from all workloads **except** the Ingress Gateway.
- 📡 L7 policy enforced **method-level** access (`GET` only) from a specific workload identity.
- ✅ Kiali can be used to visualize and confirm that **only authorized traffic** is flowing to your services.

---

---

## 🔐 Certificate Management in Istio Ambient Mode

### Background: Why Manage Certificates?

Istio uses **mutual TLS (mTLS)** for secure communication between services in the mesh. This requires issuing and managing certificates to workloads so they can authenticate and encrypt traffic.

---

### How Certificate Issuance Works in Ambient Mode

1. **Workload Starts**
   When a workload (pod) starts on a node, the **CNI agent** informs the **Ztunnel** (Istio’s ambient mode sidecar proxy replacement) that a new workload is running.

2. **Ztunnel Requests Certificate**
   Ztunnel acts as the **xDS client** and connects to the Istio control plane component **Istiod** to request a certificate for the workload it represents.

3. **Istiod Verifies Request**
   Istiod checks that the workload is actually running on the node from which the request originated (to prevent spoofing).

4. **Certificate Signing**
   Once validated, Istiod signs the certificate and returns it to Ztunnel.

5. **Certificate Delivered**
   Ztunnel provides the signed certificate to the workload, enabling secure mTLS communication inside the mesh.

6. **Renewal**
   When certificates expire, **Ztunnel automatically handles certificate renewal** transparently.

---

### Generating and Installing Custom Certificates

You can generate your own **Root CA and Intermediate CA certificates** for Istio to use instead of the default ones. This is important for production-grade security and compliance.

#### Step-by-Step Process:

1. **Create a directory** to store your certificates and switch to it.
   `mkdir ca-cert`
   `cd ca-certs`
   `make -f ..k8s//tools/certs/Makefile.selfsigned.mk root-ca`
   `ls`

2. **Generate the Root CA certificate and key**

   - Using Istio’s sample Makefile or OpenSSL, generate:

     - `root-ca.conf` (OpenSSL config)
     - `root-cert.csr` (certificate signing request)
     - `root-cert.pem` (root CA certificate)
     - `root-key.pem` (root key)

3. **Generate an Intermediate CA certificate and key**

   - Use the root CA to sign the intermediate CA (e.g., named `istio-cluster`) to avoid using the root CA directly, which is a best practice.
     `make -f ../tools/certs/Makefile.selfsigned.mk istio-cluster-cacerts`
     `cd istio-cluster`

4. **Create a Kubernetes secret in the `istio-system` namespace** with these certificates:

   ```bash
   kubectl create namespace istio-system
   kubectl create secret generic cacerts -n istio-system \
     --from-file=root-cert.pem=path/to/root-cert.pem \
     --from-file=root-key.pem=path/to/root-key.pem \
     --from-file=cert-chain.pem=path/to/intermediate-cert.pem \
     --from-file=key.pem=path/to/intermediate-key.pem
   ```

5. **Install or reinstall Istio** with these certificates.

   - Either delete your existing Istio installation and redeploy, or start a fresh cluster and install Istio.
   - Use a script or Istioctl to deploy Istio and your sample apps (like Bookinfo).
     `./install.sh`

6. **Label your application namespaces** with `istio.io/dataplane-mode=ambient` to enable ambient mode proxying.
   `kubectl get pods -n bookinfo`
   `kubectl label namespace bookInfo istio.io/dataplane-mode=ambient`
   `curl http://localhost:80/productpage`

---

### Verifying Certificates in Use

- Check the **Ztunnel pod** which holds the certificates in ambient mode.

`kubectl get pods -n istio-system`

- Use Istioctl to inspect certificates:

  ```bash
  istioctl ztunnel-config certificate <ztunnel-pod-name> -n <namespace>

  or

    istioctl ztunnel-config certificate <ztunnel-pod-name>.istio-system>
  ```

- Extract and compare the certificates inside Ztunnel with the certificates you created locally using:

  ```bash
  istioctl ztunnel-config certificate ztunnel-h8581.istio-system -o json jq -r '.[0].certChain[0].pem' | base64 -d openssl x509 -text - nout > ztunnel-cert;crt.txt
  ```

```
x509 -in ca-certs/istio-cluster/root-cert.pem > root-cert.crt.txt

diff -s root-cert.txt ztunnel-cert.crt.txt
diff -s ca-cert.txt ztunnel.crt.txt
```

compare

- Matching files confirm that Istio is using your custom Root CA and certificates correctly.

---

### Important Notes for Production

- The manual certificate generation process is fine for demos and labs.
- For production, consider using **robust external certificate authorities** like **HashiCorp Vault** or a managed CA solution for secure, automated certificate lifecycle management.

---

### Summary

| Step                        | Description                                       |
| --------------------------- | ------------------------------------------------- |
| Workload starts             | CNI informs Ztunnel of new workload               |
| Ztunnel requests cert       | Connects to Istiod, authenticates node & workload |
| Istiod signs & returns cert | Signs certificate & sends back                    |
| Ztunnel delivers cert       | Provides cert to workload for mTLS                |
| Certificate renewal         | Ztunnel auto-renews expired certs                 |
| Custom cert generation      | Generate root and intermediate CA certs           |
| Create Kubernetes secret    | Store certs in `istio-system` namespace           |
| Deploy Istio with certs     | Fresh install or reinstall using your certs       |
| Verify cert usage           | Use `istioctl` and `diff` to confirm certs        |

---

---

## 📊 Introduction to Monitoring in Istio

### Why Monitoring Matters

As your application scales, things can start to go wrong: pages might load slowly, services may fail, or unexpected errors could occur. When this happens, the key challenge is understanding **what’s causing the problem**. For example:

- Is the **rating service** too slow?
- Did the **review service crash**?
- Or is it something else entirely?

---

### What Istio Brings to Observability

Istio helps by providing **deep visibility into your application’s behavior** — often called **observability**. This means you get clear insights into how your services are performing and communicating behind the scenes.

---

### How Istio Collects Monitoring Data in Ambient Mode

In an **ambient mesh**, Istio collects telemetry data mainly from two components:

- **Ztunnel proxies** (which handle the workload-level communication)
- **Waypoint proxies** (which handle ingress/egress traffic)

---

### The Three Pillars of Istio Monitoring Data

Istio breaks down its monitoring data into three key categories:

| Data Type              | Description                                                                 | Use Cases                                    |
| ---------------------- | --------------------------------------------------------------------------- | -------------------------------------------- |
| **Metrics**            | Quantitative data like request counts, latencies, error rates               | Overall health & performance tracking        |
| **Access Logs**        | Logs of every request with info about source, destination, and status       | Troubleshooting, auditing, forensic analysis |
| **Distributed Traces** | Visual maps of how requests travel through services, showing latency points | Pinpoint bottlenecks, latency, or failures   |

---

### Why This Matters

With Istio’s monitoring tools, you can:

- **Catch issues early** before users notice problems
- **Fix problems quickly** with detailed diagnostics
- **Keep your app running smoothly** by continuously observing service health and interactions

---

---

## 📈 Visualizing Metrics with Prometheus and Grafana in Istio

### Why Visualize Metrics?

Visualizing metrics helps you understand what's happening with your services **in real time** so you can quickly spot performance issues and fix them before they impact users.

---

### The Tools: Prometheus and Grafana

- **Prometheus:**
  An open-source monitoring tool that **collects and stores metrics** from your services. It gathers data such as:

  - Traffic volume
  - Error counts
  - Response times

- **Grafana:**
  A powerful visualization tool that takes data from Prometheus and turns it into **interactive graphs and dashboards**, making it easier to interpret metrics visually.

---

### Key Istio Metrics to Monitor

Istio provides essential metrics to track the health and performance of your services:

| Metric     | What It Shows                      | Why It Matters           |
| ---------- | ---------------------------------- | ------------------------ |
| Latency    | How quickly services respond       | Identify slowdowns       |
| Traffic    | Volume of requests handled         | Understand demand & load |
| Errors     | Frequency of failures or errors    | Detect problems          |
| Saturation | How close services are to overload | Prevent service crashes  |

Together, these metrics give you a **clear picture of your system’s performance** and where you may need to act.

---

### Setting Up Prometheus

1. **Check if Prometheus is running:**

   ```bash
   kubectl get svc -n istio-system prometheus
   ```

   If it’s not running, install it using the provided manifests (`prometheus.yaml`).

   kubectl apply -f prometheus.yaml -n istio-system

2. **Generate traffic:**
   Run a command to generate load on your BookInfo app, so metrics start flowing.

   ```bash
   for i in $(seq 1 100); do
   curl -s http://localhost:productpage
   done

   ```

3. **Access Prometheus UI:**
   Use Istioctl to open Prometheus:

   ```bash
   istioctl dashboard prometheus
   ```

````

4. **Query metrics:**
   Example queries include:

   - Total requests:

     ```
     istio_requests_total
     ```

   - Requests to the product page:

     ```
     istio_requests_total{destination_service="productpage.bookinfo.svc.cluster.local"}
     ```

   - Requests to reviews service version 3:

     ```
       istio_requests_total{destination_service="reviews.bookinfo.svc.cluster.local",destination_version="v3"}
     ```

   - Request rate over 5 minutes in products page:

     ```
     rate(istio_requests_total{destination_service="productpage.*", response_code="200"}[5m])
     ```

---

### Setting Up Grafana

1. **Install Grafana:**
   Apply the manifest to the `istio-system` namespace:

   ```bash
   kubectl apply -f grafana.yaml -n istio-system
   ```

2. **Open Grafana Dashboard:**
   Use Istioctl to open Grafana:

   ```bash
   istioctl dashboard grafana
   ```

3. **Explore Prebuilt Dashboards:**
   Grafana includes several dashboards out of the box:

   - **Control Plane Dashboard**
   - **Service Dashboard**
   - **Workload Dashboard**
   - **Istio Service Dashboard** (deep dive into individual services)

---

### Summary

- Prometheus **collects** detailed metrics from your Istio service mesh.
- Grafana **visualizes** these metrics, giving you intuitive, real-time insight.
- Together, they provide a powerful monitoring solution to keep your Istio mesh healthy and performant.

---

---

## 🔍 Distributed Tracing with Jaeger in Istio

### What Is Distributed Tracing?

- While **metrics** provide an overall picture of how your services are performing, **distributed tracing** lets you **follow individual requests** step-by-step as they flow through your service mesh.
- Imagine tracing a package delivery — you can see every stop it makes and how long it spends at each stage.
- This helps you pinpoint exactly where slowdowns, errors, or failures occur within your microservices.

---

### Why Use Jaeger?

- **Jaeger** is a popular open-source tool for distributed tracing.
- It acts like a GPS for your application, showing the full path of each request as it moves across your services.
- Istio supports multiple tracing backends (Jaeger, Zipkin, Datadog, etc.), but Jaeger is often used because of its integration and features.

---

### How to Enable Tracing with Jaeger in Istio

1. **Enable tracing in Istio's mesh config:**

   - Set `enableTracing: true` in the mesh config to start collecting trace data.
   - Clean up old tracing configs by setting tracing to the MT (multi-tenant) config.
   - Configure the tracing provider in the extension provider section to point to Jaeger via OpenTelemetry.


2. **Enable telemetry:**

   - Make sure telemetry is enabled (`enabled: true`) so Istio collects both metrics and tracing data for full visibility.

3. **Apply configuration:**

   - If you installed Istio via Helm, apply these changes using a `helm upgrade` with the updated values file.
   - Confirm Istio pods (like `istiod`) are running before upgrading.

4. **Set up the Jaeger collector:**

   - Deploy Jaeger to listen for incoming trace data from Istio.
   - Modify `telemetry.yaml` to send all traces to the Jaeger collector.



```bash
kubectl get pods -n istio-system  # to confirm is istiod is running

helm upgrade istio/istiod -n istio-system --set profile-ambient --wait --values k8s/monitorting//tracing/tracing-values.yaml

kubectl apply -f k8s/monitorting//tracing/telemetry.yaml

```

   ```bash
   for i in $(seq 1 100); do
   curl -s http://localhost:productpage
   done

   ```

Apply delay and tracse the delay with jaeger

   ```bash
   kubectl apply -f  k8s/monitorting//tracing/delay.yamml -n bookInfo
   ```



      ```bash
   for i in $(seq 1 100); do
   curl -s http://localhost:productpage
   done

   ```
---

### Using Jaeger to Visualize Traces

- **Generate traffic** on your application to create trace data.
- Open the Jaeger UI with:

  ```bash
  istioctl dashboard jaeger
  ```

- In the **Search tab**:

  - Select the service you want to view traces for (e.g., `istio-ingressgateway`).
  - Add filters like tags or operation types if needed.
  - Set the number of traces to display (e.g., 50 or 100).

- View individual traces, which include **spans** showing each step the request took across services.
- Inspect timings and errors within the trace to identify slow or failing parts.

---

### Example: Introducing Latency and Observing Effects

- You can simulate delays (like adding a 10-second delay in the `details` service) by creating a **Virtual Service** that injects latency.
- After applying the delay and generating traffic, you can observe:

  - Red error indicators in tools like **Kiali** on the affected services.
  - Errors and increased latency reflected in Jaeger traces, with the affected spans marked accordingly.

This demonstrates how distributed tracing helps you quickly identify and diagnose service-level issues.

---

### Summary

- Distributed tracing lets you **follow each request’s journey** across your microservices.
- Jaeger provides a rich, interactive UI to explore these traces.
- Enabling tracing in Istio and setting up Jaeger gives you **deep insight** to find and fix issues quickly.
- Combined with other observability tools (metrics, logs), tracing completes your visibility into how your service mesh performs.

---

---

## 🔍 Visualizing Your Service Mesh with Kiali

### What is Kiali?

- Kiali is a powerful **observability tool** designed specifically for **service mesh** environments like Istio.
- It helps you **monitor, visualize, and troubleshoot** your microservices by providing real-time insights into how services interact within your mesh.
- Beyond simple visualization, Kiali also checks for **configuration errors** and displays health status for services and namespaces.

---

### How to Access Kiali

- You can access the Kiali dashboard by running the following command to open a local port forward to your Kiali instance:

  ```bash
  istioctl dashboard kiali
  ```

- This opens a web UI where you can explore your mesh data visually.

---

### Kiali Overview Page

- The first screen you see gives you an **overview of all namespaces and applications** deployed in your mesh.
- For each namespace, Kiali displays:

  - The list of deployed applications and services.
  - The **health status** indicators:

    - **Green:** Everything is healthy.
    - **Yellow or Red:** Issues detected, such as failed requests or misconfigurations.

- You can click on a namespace or service to drill down for more details.

---

### Traffic Graph — Visualizing Service Interactions

- The **traffic graph** is one of Kiali’s most useful features.
- It shows a **graphical representation of all services** and how they communicate with each other.
- To see live traffic data:

  - Generate traffic on your application (e.g., by running load or test commands).
  - Refresh the Kiali dashboard to see updated graphs.

- The graph illustrates:

  - Services (nodes) like `product page`, `reviews`, `ratings`, etc.
  - Connections between services (edges) representing traffic flow.
  - Incoming traffic through `istio-ingressgateway`.
  - Different versions of services if deployed.

---

### Inspecting Metrics on the Traffic Graph

- Hovering or clicking on connections between services reveals key metrics:

  - Request rates.
  - Success and error percentages.
  - Latency or other performance indicators.

- This helps quickly identify bottlenecks or failing connections.

---

### Detailed Service View

- Clicking on a service node (e.g., `product page`) opens a detailed view.
- Here, you can explore:

  - Inbound and outbound traffic metrics.
  - TCP metrics like TCP opened, TCP closed, and TCP received.
  - Other relevant service health and performance metrics.

- You can customize and filter metrics as needed.

---

### Configuration Validation

- Kiali also helps detect **configuration errors**.
- Example: If you define a **destination rule** referencing a non-existent service version (like version `v4` for reviews which isn’t deployed), Kiali will show an error.
- This immediate feedback helps avoid misconfigurations before applying them.
- Fixing the config (e.g., removing the invalid version subset) removes the error warning.

---

### Filtering and Exploring Resources

- You can filter views by resource types such as:

  - Authorization policies.
  - Destination rules.
  - Virtual services.

- This makes it easier to manage complex configurations in your mesh.

---

### Security Insights with Mutual TLS (mTLS)

- In the traffic graph, you can enable the **Security tab** to see:

  - Which services are communicating using **mutual TLS (mTLS)**.
  - This visual overlay helps verify secure communication within the mesh.

---

### Additional Features

- **Waypoint Proxy view:** See detailed internal communication within your mesh.
- Kiali is more than a visualization tool; it’s a **full observability platform** with extensive capabilities for:

  - Monitoring.
  - Troubleshooting.
  - Security validation.
  - Configuration management.

---

### Summary

- **Kiali helps you visualize and monitor your Istio service mesh in real-time.**
- It provides a graphical map of service communication with rich metrics.
- Detects errors in your configuration before they impact your system.
- Supports filtering by resource type and viewing security settings like mTLS.
- The more you use Kiali, the easier it becomes to manage and troubleshoot complex microservice architectures.

---
````
