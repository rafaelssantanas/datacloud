## Postman Configuration

### Introduction

This tutorial aims to introduce the initial configurations for using Postman to communicate with **Salesforce Data Cloud**. The focus will be on ensuring an efficient, secure, and optimized integration when interacting with the platform.

> [!NOTE]
> Salesforce provides a trail [Connect Postman to Salesforce](https://trailhead.salesforce.com/en/content/learn/projects/quick-start-connect-postman-to-salesforce) and a tutorial video [Data Cloud Connect APIs and Postman Quick Start Video](https://salesforce.vidyard.com/watch/cTet8JYsu9zd6QsqxFkkwN) to help developers configure and test Salesforce Data Cloud APIs using Postman. However, this documentation offers a more comprehensive approach, presenting additional best practices for configuring your environment more efficiently.

An **Application Programming Interface** (API) is a set of rules and protocols that defines communication between systems, allowing structured and standardized data and functionality exchange. APIs play essential roles such as data validation, information integration, process automation, and application development. In the context of Salesforce Data Cloud development, they enable access, querying, and validation of stored data, ensuring its integrity and accuracy.

To interact with these APIs efficiently, tools simplify request sending, response visualization, and authentication management, such as Postman, which will be covered next.
<br>

### Postman

**Postman** is a useful tool for testing APIs, allowing users to create, send, and automate HTTP requests. An HTTP request is a system-to-system request to obtain or send information over the internet. It functions as a structured request, where a client (such as a browser or an application) sends a request to a server, which, in turn, returns a response with the requested data.

Thus, Postman facilitates response visualization, authentication management, and organization of API call collections, optimizing platform interaction.
<br>

### Data Cloud Connect Collection

The **Data Cloud Connect API** Postman Collection, provided by Salesforce, organizes and simplifies interactions with the platform's services. It enables API calls within workflows, making it easier to manipulate and request data essential for operations such as data ingestion, segmentation, and audience activation.

Next, we will detail the necessary activities for configuring the environment and effectively using the tools, ensuring an optimized integration with the platform.
<br>

---

#### 1. Creating a Workspace

Postman is available in two versions: a desktop application and a web version. Choose the best option based on your usage preferences and work environment needs.

1. Access your **[Postman](https://www.postman.com/)** account or create one if you haven't yet.
2. In the menu, select `Workspaces`.
3. Click on `Create Workspace`.
4. Name the workspace `Salesforce Collection`.
5. Set the `Visibility` option to `Personal`.
6. Click `Create Workspace` to finalize.
   <br>

#### 2. Forking the Salesforce Collection

Creating a fork is essential to ensure you have an independent copy of the original collection. This allows you to make modifications and customizations without affecting the original version, offering greater control and security during development. Additionally, when forking, you can adjust variables and credentials specific to your organization, facilitating management and avoiding impacts on other configurations.

1. Access the **[Salesforce Developers](https://www.postman.com/salesforce-developers/salesforce-developers/overview)** public workspace to fork the Salesforce API collection.
2. Under `Collections`, navigate to `Salesforce Data Cloud Connect APIs`.
3. Click the three dots in the top-right corner to expand options and select `Create a fork`.
4. Name the collection `DataCloudFork`.
5. Select the Salesforce Collection workspace created earlier.
6. Click `Fork Collection` to finalize.
   <br>

#### 3. Configuring a New Environment

As a developer, you may have access to multiple organizations. To optimize management, we will create a new environment to store variables and configure credentials for a specific organization.

1. In the upper-right corner, under `No Environment`, click the `+` icon and select `Create Environment`.
2. Assign a name to the environment, preferably using the project name for reference.
3. Click `Collections` to return to the page of the forked collection.
4. Then, in the top-right corner, click `Variables`.
5. Copy the existing variables and add them to the newly created environment, ensuring all necessary variables are preserved.
6. Update relevant project information, such as `clientId`.
7. After copying and updating variable values, save the configurations.
8. Return to the collection and deselect variable fields to avoid conflicts. The variables to be used will be available at the environment level.
9. Finally, save the information in the collection's variable tab.
   <br>

#### 4. Authorizing Your Organization

You need to authenticate with Salesforce to access the APIs. This process grants an access token valid for a specific period. If the token expires, you will need to repeat the authentication process.

1. Log in to your organization using a browser.
2. In Postman, under `Collections`, select the forked collection. Then, click `Authorization`. The authentication type (Auth Type) should be set to `OAuth 2.0`.
3. Scroll down and click `Get New Access Token`.
4. A new window will appear requesting access confirmation. Click `Allow`.
5. After credential validation, a success message will appear, and you will be redirected to the `Manage Access Tokens` screen. If you haven't updated your instance URL, copy the `instance_url` value, which should be updated in step 7.
6. Click `Use Token`.
7. Open the `Variables` tab and, in the `dne_cdpInstanceUrl` row, insert the `instance_url` value copied in step 5.
8. Click `Save`.

#### 5. Connection Validation

Finally, we will validate the connection to ensure everything is functioning correctly.

1. Select the forked collection to expand the list of options.
2. Click `Auth` to expand the settings, then select the `GET` `User Info` option.
3. Check if the request status is `200 OK`, indicating successful authentication.
4. If necessary, enable the `Follow Authorization Header` setting in the `Settings` tab. This option ensures the authorization header is preserved when redirected to a different hostname.

After successful authentication, you will be ready to use other requests within the collection.
