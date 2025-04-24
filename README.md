# Delta Lake in Azure Databricks Lab

## Title
**Use Delta Lake in Azure Databricks**

## Overview
Delta Lake is an open source project that builds a transactional data storage layer for Apache Spark on top of a data lake. Delta Lake supports relational semantics for both batch and streaming data operations, enabling the creation of a Lakehouse architecture.

This lab takes approximately **40 minutes** to complete.

---

## Prerequisites
- An Azure subscription with **administrative-level access**

---

## Provision an Azure Databricks Workspace

### Steps:
1. Go to [https://portal.azure.com](https://portal.azure.com).
2. Launch **Cloud Shell** via the [>_] button near the search bar.
   - Select **PowerShell**.
   - Create storage if prompted.
3. Run the following commands to clone the GitHub repository:

```powershell
rm -r dp-203 -f
git clone https://github.com/MicrosoftLearning/dp-203-azure-data-engineer dp-203
```

4. Change directory and run setup script:

```powershell
cd dp-203/Allfiles/labs/25
./setup.ps1
```

5. Choose your subscription if prompted. Wait ~5 minutes for setup to complete.

---

## Create a Cluster

1. Go to the Azure portal and find your **dp203-xxxxxxx** resource group.
2. Open the **Azure Databricks Service** (named like `databricksxxxxxxx`).
3. Click **Launch Workspace**.
4. In the workspace portal, click the **(+) New** button and select **Cluster**.
5. Use the following settings:
   - **Cluster name**: Default or your own
   - **Cluster mode**: Single Node
   - **Access mode**: Single user (your account)
   - **Runtime version**: 13.3 LTS (Spark 3.4.1, Scala 2.12)
   - **Use Photon Acceleration**: Enabled
   - **Node type**: Standard_DS3_v2
   - **Terminate after**: 30 minutes

> **Note**: Cluster startup issues may be due to regional quotas. You can rerun setup in another region using:
```powershell
./setup.ps1 eastus
```

---

## Explore Delta Lake Using a Notebook

1. In Databricks workspace portal, go to **Workspace > ⌂ Home**.
2. Next to your username, click the **⋮ (More Options)** menu > **Import**.
3. Choose **URL** and paste:

```
https://github.com/MicrosoftLearning/dp-203-azure-data-engineer/raw/master/Allfiles/labs/25/Delta-Lake.ipynb
```

4. Open the notebook and attach it to your cluster.
5. Run the cells and follow the notebook instructions to explore Delta Lake.

---

## Clean Up Resources

1. Close the Databricks tab and return to the Azure portal.
2. Go to **Home > Resource groups**.
3. Find and select your **dp203-xxxxxxx** resource group.
4. Click **Delete resource group**.
5. Confirm by entering the resource group name.
6. Wait a few minutes for all associated resources to be deleted.

---

## Resources
- [Azure Cloud Shell Documentation](https://learn.microsoft.com/en-us/azure/cloud-shell/overview)
- [Delta Lake Documentation](https://learn.microsoft.com/en-us/azure/databricks/delta/)

---

Happy Learning! 🌟

