---
title: Configure Lexmark Cloud Services (SAML) for automatic user provisioning with Microsoft Entra ID
description: Learn how to automatically provision and de-provision user accounts from Microsoft Entra ID to Lexmark Cloud Services (SAML).

author: jeevansd
manager: jeedes
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 12/05/2025
ms.author: jeevansd

# Customer intent: As an IT administrator, I want to learn how to automatically provision and deprovision user accounts from Microsoft Entra ID to Lexmark Cloud Services (SAML) so that I can streamline the user management process and ensure that users have the appropriate access to Lexmark Cloud Services (SAML).

---

# Configure Lexmark Cloud Services (SAML) for automatic user provisioning

This article describes the steps you need to perform in both Lexmark Cloud Services (SAML) and Microsoft Entra ID to configure automatic user provisioning. When configured, Microsoft Entra ID automatically provisions and de-provisions users and groups to Lexmark Cloud Services (SAML) using the Microsoft Entra provisioning service. For important details on what this service does, how it works, and frequently asked questions, see [Automate user provisioning and deprovisioning to SaaS applications with Microsoft Entra ID](~/identity/app-provisioning/user-provisioning.md). 


## Capabilities supported
> [!div class="checklist"]
> * Create users in Lexmark Cloud Services (SAML).
> * Remove users in Lexmark Cloud Services (SAML) when they don't require access anymore.
> * Keep user attributes synchronized between Microsoft Entra ID and Lexmark Cloud Services (SAML).
> * Provision groups and group memberships in Lexmark Cloud Services (SAML).
> * [Single sign-on](adobe-identity-management-tutorial.md) to Lexmark Cloud Services (SAML) (recommended).

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

* [A Microsoft Entra tenant](~/identity-platform/quickstart-create-new-tenant.md).
* One of the following roles: [Application Administrator](/entra/identity/role-based-access-control/permissions-reference#application-administrator), [Cloud Application Administrator](/entra/identity/role-based-access-control/permissions-reference#cloud-application-administrator), or [Application Owner](/entra/fundamentals/users-default-permissions#owned-enterprise-applications). 
* A federated directory in the [Adobe Admin Console](https://adminconsole.adobe.com/) with verified domains.
* Review the [adobe documentation](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/add-azure-sync.ug.html) on user provisioning 

> [!NOTE]
> If your organization uses the User Sync Tool or a UMAPI integration, you must first pause the integration. Then, add Microsoft Entra automatic provisioning to automate user management. Once Microsoft Entra automatic provisioning is configured and running, you can completely remove the User Sync Tool or UMAPI integration.

> [!NOTE]
> This integration is also available to use from Microsoft Entra US Government Cloud environment. You can find this application in the Microsoft Entra US Government Cloud Application Gallery and configure it in the same way as you do from public cloud.

## Step 1: Plan your provisioning deployment
1. Learn about [how the provisioning service works](~/identity/app-provisioning/user-provisioning.md).
2. Determine who is in [scope for provisioning](~/identity/app-provisioning/define-conditional-rules-for-provisioning-user-accounts.md).
3. Determine what data to [map between Microsoft Entra ID and Lexmark Cloud Services (SAML)](~/identity/app-provisioning/customize-application-attributes.md). 

<a name='step-2-configure-adobe-identity-management-saml-to-support-provisioning-with-azure-ad'></a>

## Step 2: Configure Lexmark Cloud Services (SAML) to support provisioning with Microsoft Entra ID

1. Log in to [Adobe Admin Console](https://adminconsole.adobe.com/). Navigate to **Settings > Directory Details > Sync**. 

2. Select **Add Sync**.

    ![Screenshot shows to add.](media/adobe-identity-management-provisioning-saml-tutorial/add-sync.png "Add")

3. Select **Sync users from Microsoft Azure** and select **Next**.

    ![Screenshot that shows 'Sync users from Microsoft Entra ID' selected.](media/adobe-identity-management-provisioning-saml-tutorial/sync-users.png)

4. Copy and save the **Tenant URL** and the **Secret token**. These values are entered in the **Tenant URL** and **Secret Token** fields in the Provisioning tab of your Lexmark Cloud Services (SAML) application.

    ![Screenshot shows to sync.](media/adobe-identity-management-provisioning-saml-tutorial/token.png "Sync")

<a name='step-3-add-adobe-identity-management-from-the-azure-ad-application-gallery'></a>

## Step 3: Add Lexmark Cloud Services (SAML) from the Microsoft Entra application gallery

Add Lexmark Cloud Services (SAML) from the Microsoft Entra application gallery to start managing provisioning to Lexmark Cloud Services (SAML). If you have previously setup Lexmark Cloud Services (SAML) for SSO, you can use the same application. However it's recommended that you create a separate app when testing out the integration initially. Learn more about adding an application from the gallery [here](~/identity/enterprise-apps/add-application-portal.md). 

## Step 4: Define who is in scope for provisioning 

[!INCLUDE [create-assign-users-provisioning.md](~/identity/saas-apps/includes/create-assign-users-provisioning.md)]

## Step 5: Configure automatic user provisioning to Lexmark Cloud Services (SAML) 

This section guides you through the steps to configure the Microsoft Entra provisioning service to create, update, and disable users and/or groups in TestApp based on user and/or group assignments in Microsoft Entra ID.

### To configure automatic user provisioning for Lexmark Cloud Services (SAML) in Microsoft Entra ID:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Identity** > **Applications** > **Enterprise applications**

    ![Screenshot shows the enterprise applications blade.](common/enterprise-applications.png "Enterprise application")

1. In the applications list, select **Lexmark Cloud Services (SAML)**.

    ![Screenshot shows the Lexmark Cloud Services (SAML) link in the Applications list.](common/all-applications.png "Application List")

3. Select the **Provisioning** tab.

    ![Screenshot shows the provisioning tab.](common/provisioning.png "Tab")

4. Set the **Provisioning Mode** to **Automatic**.

    ![Screenshot shows the provisioning tab automatic.](common/provisioning-automatic.png "Provisioning tab")

5. Under the **Admin Credentials** section, input your Lexmark Cloud Services (SAML) Tenant URL and Secret Token retrieved earlier from Step 2. Select **Test Connection** to ensure Microsoft Entra ID can connect to Lexmark Cloud Services (SAML). If the connection fails, ensure your Lexmark Cloud Services (SAML) account has Admin permissions and try again.

    ![Screenshot shows the Token.](common/provisioning-testconnection-tenanturltoken.png "Token")

6. In the **Notification Email** field, enter the email address of a person or group who should receive the provisioning error notifications and select the **Send an email notification when a failure occurs** check box.

    ![Screenshot shows the Notification Email.](common/provisioning-notification-email.png "Notification Email")

7. Select **Save**.

8. Under the **Mappings** section, select **Synchronize Microsoft Entra users to Lexmark Cloud Services (SAML)**.

9. Review the user attributes that are synchronized from Microsoft Entra ID to Lexmark Cloud Services (SAML) in the **Attribute-Mapping** section. The attributes selected as **Matching** properties are used to match the user accounts in Lexmark Cloud Services (SAML) for update operations. If you choose to change the [matching target attribute](~/identity/app-provisioning/customize-application-attributes.md), you need to ensure that the Lexmark Cloud Services (SAML) API supports filtering users based on that attribute. Select the **Save** button to commit any changes.

   |Attribute|Type|Supported for filtering|Required by Lexmark Cloud Services (SAML)
   |---|---|---|---|
   |userName|String|&check;|&check;   
   |active|Boolean||
   |emails[type eq "work"].value|String||
   |addresses[type eq "work"].country|String||
   |name.givenName|String||
   |name.familyName|String||
   |urn:ietf:params:scim:schemas:extension:Adobe:2.0:User:emailAliases|String||
   |urn:ietf:params:scim:schemas:extension:Adobe:2.0:User:eduRole|String||

    > [!NOTE]
    > The **eduRole** field accepts values like `Teacher or Student`, anything else is ignored.

10. Under the **Mappings** section, select **Synchronize Microsoft Entra groups to Lexmark Cloud Services (SAML)**.

11. Review the group attributes that are synchronized from Microsoft Entra ID to Lexmark Cloud Services (SAML) in the **Attribute-Mapping** section. The attributes selected as **Matching** properties are used to match the groups in Lexmark Cloud Services (SAML) for update operations. Select the **Save** button to commit any changes.

      |Attribute|Type|Supported for filtering|Required by Lexmark Cloud Services (SAML)
      |---|---|---|---|
      |displayName|String|&check;|&check;
      |members|Reference||

12. To configure scoping filters, refer to the following instructions provided in the [Scoping filter  article](~/identity/app-provisioning/define-conditional-rules-for-provisioning-user-accounts.md).

13. To enable the Microsoft Entra provisioning service for Lexmark Cloud Services (SAML), change the **Provisioning Status** to **On** in the **Settings** section.

    ![Screenshot shows the Provisioning Status Toggled On.](common/provisioning-toggle-on.png "Provisioning status")

14. Define the users and/or groups that you would like to provision to Lexmark Cloud Services (SAML) by choosing the desired values in **Scope** in the **Settings** section.

    ![Screenshot shows the Provisioning Scope.](common/provisioning-scope.png "Provisioning Scope")

15. When you're ready to provision, select **Save**.

    ![Screenshot shows the Saving Provisioning Configuration.](common/provisioning-configuration-save.png "Configuration")

This operation starts the initial synchronization cycle of all users and groups defined in **Scope** in the **Settings** section. The initial cycle takes longer to perform than subsequent cycles, which occur approximately every 40 minutes as long as the Microsoft Entra provisioning service is running. 

## Step 6: Monitor your deployment

[!INCLUDE [monitor-deployment.md](~/identity/saas-apps/includes/monitor-deployment.md)]

## Change log
* 07/18/2023 - The app was added to Gov Cloud.
* 08/15/2023 - Added support for Schema Discovery.

## More resources

* [Managing user account provisioning for Enterprise Apps](~/identity/app-provisioning/configure-automatic-user-provisioning-portal.md)
* [What is application access and single sign-on with Microsoft Entra ID?](~/identity/enterprise-apps/what-is-single-sign-on.md)

## Related content

* [Learn how to review logs and get reports on provisioning activity](~/identity/app-provisioning/check-status-user-account-provisioning.md)
