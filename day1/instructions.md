### **Day 1, Part 3: Azure Kubernetes Service (AKS) - Actionable Steps**

#### **Setting Up an AKS Cluster**:

1. **Azure Portal & Azure CLI Setup**:
   
   **Azure Portal**:
   - Go to [Azure Portal](https://portal.azure.com/).
   - Log in using your Azure credentials.
   - Ensure you have the necessary permissions to create resources.

   **Azure CLI**:
   - Download and install the Azure CLI from the [official website](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli).
   - Once installed, open your terminal or command prompt.
   - Authenticate with Azure using:
     ```bash
     az login
     ```
     Follow the prompted instructions.

2. **Resource Groups**:

   **Azure Portal**:
   - On the left sidebar, click on `Resource groups`.
   - Click on `+ Add` to create a new resource group.
   - Choose a suitable name and region, then click on `Review + create`.

   **Azure CLI**:
   ```bash
   az group create --name <ResourceGroupName> --location <RegionName>
   ```

3. **AKS Cluster Creation**:

   **Azure Portal**:
   - In the Azure Portal search bar, type “Kubernetes services” and select it.
   - Click on `+ Add`.
   - Select your previously created resource group.
   - Enter a unique name for the AKS cluster.
   - Adjust the region, node size, and count as per your needs.
   - Review other settings and adjust as necessary, then click on `Review + create`.

   **Azure CLI**:
   ```bash
   az aks create --resource-group <ResourceGroupName> --name <ClusterName> --node-count 1 --enable-addons monitoring --generate-ssh-keys
   ```

4. **Kubectl Configuration**:

   **Azure CLI** (as this step typically uses CLI tools):
   - First, install `kubectl`:
     ```bash
     az aks install-cli
     ```
   - Then, configure `kubectl` to communicate with your AKS cluster:
     ```bash
     az aks get-credentials --resource-group <ResourceGroupName> --name <ClusterName>
     ```

   **Testing your setup**:
   - Check nodes in your AKS cluster:
     ```bash
     kubectl get nodes
     ```

---

#### **Cost Management on Azure**:

1. **Monitoring and Budgeting**:

   **Azure Portal**:
   - Go to [Azure Cost Management and Billing](https://portal.azure.com/#blade/Microsoft_Azure_Billing/ModernBillingMenuBlade/Overview).
   - Under `Cost Management`, click on `Budgets`.
   - Click on `+ Add` to set up a new budget.
   - Define criteria (scope, reset period, etc.), and set a budget amount.
   - Configure alerts at certain percentages of your budget.

