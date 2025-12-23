---
tags: Data Infrastructure
description: Connect with Databricks to run data pipelines and advanced analytics seamlessly.
---


# Databricks Integration

The **Databricks Integration** allows your app to connect to [Databricks](https://www.databricks.com/) for secure data access, querying, and analytics. Once connected, you can run SQL queries, retrieve results, and power data-driven workflows directly from your app.

## What You Can Do

With Databricks, your app can:
- Connect securely to your Databricks workspace.  
- Run **SQL queries** or fetch data programmatically.  
- Build **dashboards and data visualizations** on top of your Databricks tables.  
- Automate workflows triggered by new or updated data.  
- Combine Databricks with AI models for advanced analytics.



## Step 1: Get Your Databricks Credentials

### 1 - Log in to your [Databricks Workspace](https://databricks.com/).

### 2 - Get your **DATABRICKS_HOST** and **DATABRICKS_WAREHOUSE_ID**:

   - Go to `SQL Warehouses` from the sidebar.
   - Select your desired warehouse.
   - Click `Connection details`.
   - Copy the Server hostname (this is your **DATABRICKS_HOST**).
   - Copy the HTTP path removing the `/sql/1.0/warehouses/` prefix (this is your **DATABRICKS_WAREHOUSE_ID**).

![databricks_integration_1.webp](https://raw.githubusercontent.com/reflex-dev/integrations-docs/refs/heads/main/images/docs/databricks_integration_1.webp)

### 3 - Get your **DATABRICKS_CATALOG** and **DATABRICKS_SCHEMA**:
   - Click the SQL Editor from the sidebar.
   - Choose the **DATABRICKS_CATALOG** and **DATABRICKS_SCHEMA** from the dropdowns as shown below.

![databricks_integration_4.webp](https://raw.githubusercontent.com/reflex-dev/integrations-docs/refs/heads/main/images/docs/databricks_integration_4.webp)


### 4 - Obtain your authentication credentials:

There are two methods to authenticate your app with Databricks: using interactive U2M **OAuth** or via registered M2M **Service Principal**. Choose one of the methods below to obtain the necessary credentials.


---md tabs

--tab OAuth with Databricks
#### Interactive Login with your Databricks Account

If your workspace administrator has already added Reflex as a Connected App in your Databricks workspace, you should see a "Login with Databricks" button after entering your DATABRICKS_HOST.

If the Connected App has not been configured, an administrator can [follow these instructions](https://www.notion.so/Databricks-Integration-2b2024b7336e80c78e91e8a0fb138fcf?pvs=73) to complete the one-time setup.

--
--tab Service Principal
#### M2M Service Principal (DATABRICKS_CLIENT_ID and DATABRICKS_CLIENT_SECRET)

- Open the dropdown in the top right corner and select **Manage Account**.

![databricks_integration_oauth_1.webp](https://raw.githubusercontent.com/reflex-dev/integrations-docs/refs/heads/main/images/docs/databricks_integration_oauth_1.webp)

- Select `Users and Groups`

![databricks_integration_oauth_2.webp](https://raw.githubusercontent.com/reflex-dev/integrations-docs/refs/heads/main/images/docs/databricks_integration_oauth_2.webp)

- Select the `Service Principals` tab and click `Add Service Principal`.

![databricks_integration_oauth_3.webp](https://raw.githubusercontent.com/reflex-dev/integrations-docs/refs/heads/main/images/docs/databricks_integration_oauth_3.webp)

- Fill in the details and click `Add Service Principal`.

![databricks_integration_oauth_4.webp](https://raw.githubusercontent.com/reflex-dev/integrations-docs/refs/heads/main/images/docs/databricks_integration_oauth_4.webp)

- Click the `Credentials and Secrets` tab and click `Generate Secret`.

![databricks_integration_oauth_5.webp](https://raw.githubusercontent.com/reflex-dev/integrations-docs/refs/heads/main/images/docs/databricks_integration_oauth_5.webp)

- Set a lifetime for the secrets and click `Generate`.

![databricks_integration_oauth_6.webp](https://raw.githubusercontent.com/reflex-dev/integrations-docs/refs/heads/main/images/docs/databricks_integration_oauth_6.webp)

- Copy the generated **DATABRICKS_CLIENT_ID** and **DATABRICKS_CLIENT_SECRET**.

![databricks_integration_oauth_7.webp](https://raw.githubusercontent.com/reflex-dev/integrations-docs/refs/heads/main/images/docs/databricks_integration_oauth_7.webp)

--

---



## Step 2: Configure the Integration in Your App

1. In your app, go to **Integrations** and **Add Databricks**.
2. Paste your **DATABRICKS_HOST**
3. Select your authentication method:
   - OAuth, if configured.
   - Service Principal, provide the client ID and secret gathered previously.
2. Paste or select your
   1. **DATABRICKS_WAREHOUSE_ID**
   2. **DATABRICKS_CATALOG**
   3. **DATABRICKS_SCHEMA**  
3. Click **Connect** to validate and save your integration.

Once connected, the AI Builder can execute queries directly against your Databricks environment.


## Step 3: Notes

* **Secure your token:** Never expose tokens in public code.  
* **Permissions:** Ensure your token or service account has the required workspace and table permissions.
* **Combine with AI:** Use query outputs to power models, summaries, or alerts in real time.

