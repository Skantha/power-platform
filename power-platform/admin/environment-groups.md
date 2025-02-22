---
title: Environment groups (preview)
description: Learn how to organize your Managed Environments into groups and govern them in bulk with rules.
ms.component: pa-admin
ms.topic: conceptual
ms.date: 02/14/2024
author: mikferland-msft
ms.author: miferlan
ms.reviewer: sericks
ms.subservice: admin
ms.custom: "admin-security"
search.audienceType: 
  - admin
---

# Environment groups (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

The task of managing Power Platform on a large scale across numerous environments ranging from hundreds to tens of thousands poses a significant challenge for both startup and enterprise IT teams.

Similar to folders, _environment groups_ are designed to help administrators organize their flat list of environments into structured groups based on different criteria, such as business unit, project, and location.

Admins can apply various rules to groups to govern many environments in bulk, reducing manual effort and ensuring consistency. For example, admins might apply rules to security, licensing, compliance, or other facets.

> [!Important]
> - This is a preview feature.
> - Preview features aren’t meant for production use and may have restricted functionality. These features are available before an official release so that customers can get early access and provide feedback.
> - View the [Supplemental terms of use for Microsoft Power Platform and Dynamics 365 preview for online services](https://dynamics.microsoft.com/legaldocs/supp-dynamics365-preview/).

## Strategies for using environment groups

There are many ways to manage pockets of environments within your tenant using environment groups. For example, global organizations can create an environment group for all environments in each geographic region to ensure compliance with legal and regulatory requirements. You can also organize environment groups by department or other criteria.

This article covers how to augment your _default environment strategy_ by combining _environment groups_ with [_default environment routing_](default-environment-routing.md). Default environment routing gives makers their own personal developer environment. This environment is a secure space to build with Microsoft Dataverse and is similar to [OneDrive](https://www.microsoft.com/microsoft-365/onedrive/online-cloud-storage) for personal productivity.

Enabling _default environment routing_ might give you more environments to manage, but automatically creating them into a single environment group ensures they're preconfigured with important baseline controls your organization requires.

## Create an environment group

[Power Platform tenant administrators](use-service-admin-role-manage-tenant.md) can create as many environment groups as necessary to meet their organization's needs. You can create a single environment group named **Personal Productivity**, then create new developer environments into the group.

1. Sign in to [Power Platform Admin center](https://admin.powerplatform.microsoft.com/).
1. Select **Environment groups** in the navigation pane.
1. On the **Environment groups** page, select **New group**.
1. In the **Create group** pane that appears:
   1. Add a name for your group in the **Name** field such as _Personal Productivity_.
   1. Add a brief description of the group in the **Description** field.
   1. Select **Create**.

## Configure the rules for your environment group

After you create the environment group, Power Platform tenant administrators can immediately add environments or configure the group's rules. Currently, there are six available rules, which are the same capabilities offered when upgrading an _individual_ environment to a [Managed Environment](managed-environment-overview.md).

### The sharing limits rule

You can also configure the _sharing limits_ rule. Since the environment group is intended for personal productivity, makers are restricted from sharing their canvas apps with other users. This helps ensure that each environment in the group remains a private space for individual work.

1. In the **Personal Productivity** group, select the **Rules** tab.
1. Select the **Sharing Limits** rule to open its configuration panel.
1. Select **Exclude sharing with security group**.
1. Select **Limit total individuals who can share to** and enter the number **1** in the box.
1. Select **Save**.
1. Repeat these steps until all desired rules are configured.
1. Select **Publish rules**.

> [!NOTE]
> All rules are equally applied to all environments in the group.

## Route environments to your environment group

With your environment group setup, it can now serve as the home for all new personal developer environments that are created by _default environment routing_. This default ensures that all newly created developer environments are automatically preconfigured to meet baseline requirements from the start.

### Select an environment group

1. Return to the **Environment groups** page.
1. Select the **Environment Routing** button in the command bar.
1. Under the **Environment group** section, choose the group you want your new **Developer** environments to be created in.
1. Select **Save**.

> [!NOTE]
> For developer environments in the _Personal Productivity_ group, the sharing limit can't be changed in individual environment settings. The same default restriction applies to other rules. To make changes, adjust the rule and the change applies to all environments in the group.

## Manually create environments into the group

You can manually create environments into the _Personal Productivity_ group.

1. Go to the **Environments** page.
1. Select **New** in the command bar.
1. Select a **group** for your created environment.
1. Enter the other details.
1. Select **Save**.

> [!NOTE]
>
> - An environment can only belong to one environment group.
> - Only Managed Environments can be created into an environment group.
> - Any environment type, for example production, developer, or sandbox, can be created into an environment group.

## Remove an environment from your environment group

You can remove an environment from a group if it needs unique governance or if you created it by accident.

1. Select the **Personal Productivity** group.
2. Select the environment you wish to remove.
3. Select **Remove from group** in the command bar.

> [!NOTE]
>
> When you remove an environment from the group, it retains its configuration. For example, sharing canvas apps is still limited to one user. However, a removed environment is now unlocked and can be managed individually. The environment's **Edit Managed Environments** panel gets re-enabled.

## Delete an environment group

As you experiment with environment groups, you might have leftover groups that you want to delete to avoid clutter.

1. Go to the **Environment groups** page.
2. Select the environment group that you wish to delete.
3. Select **Delete group** in the command bar.

> [!IMPORTANT]
> When you delete a group, first remove all of its environments and ensure no developer environments are routed to it. If a group still has environments, you see a warning that prevents you from deleting the group.

## See also

[Managed Environments overview](managed-environment-overview.md) <br>
[Usage insights](managed-environment-usage-insights.md) <br>
[Limit sharing](managed-environment-sharing-limits.md) <br>
[Data policies](managed-environment-data-policies.md) <br>
[Licensing](managed-environment-licensing.md) <br>
[View license consumption (preview)](view-license-consumption-issues.md) <br>
[Tenant settings](tenant-settings.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
