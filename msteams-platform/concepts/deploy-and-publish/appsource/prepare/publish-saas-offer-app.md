---
title: Publish the app with SaaS offer to Teams Store
description: Learn about the go live stage, how to configure the SaaS offer to your app and publish the app to the Microsoft Teams Store.
author: v-preethah
ms.author: surbhigupta
ms.topic: how-to
ms.localizationpriority: high
ms.date: 07/11/2023
---

# Publish the app with SaaS offer

:::row:::
   :::column:::
      :::image type="icon" source="~/assets/images/saas-offer/monetize-flow1.png" link="include-saas-offer.md" border="false":::
   :::column-end:::
   :::column:::
      :::image type="icon" source="~/assets/images/saas-offer/monetize-flow2.png" link="include-saas-offer.md" border="false":::
   :::column-end:::
   :::column:::
      :::image type="icon" source="~/assets/images/saas-offer/monetize-flow3.png" link="include-saas-offer.md" border="false":::
   :::column-end:::
   :::column:::
      :::image type="icon" source="~/assets/images/saas-offer/monetize-flow4.png" link="Test-preview-for-monetized-apps.md" border="false":::
   :::column-end:::
   :::column:::
      :::image type="icon" source="~/assets/images/saas-offer/monetize-flow5a.png" link="publish-saas-offer-app.md" border="false":::
   :::column-end:::
:::row-end:::

After you create and test a software as a service (SaaS) offer, you must publish it in Microsoft commercial marketplace. This article outlines the steps to publish the SaaS offer, link the SaaS offer to your app, and publish the SaaS app. When published, the SaaS app is available for purchase in Microsoft Teams Store with the configured subscriptions.

## Go live

Upon successful testing, your can submit the offer to [Go live](/partner-center/marketplace/test-publish-saas-offer) that publishes the offer in the marketplace. The following are the phases in Go live:

1. Select **Go live** to initiate the validation checks before publishing.
1. Keep track of the publishing status on the **Offer overview** page.
1. If there are validation errors, rectify them and resubmit the offer for publishing. The errors might range from missing information to noncompliance with marketplace standards.
1. Upon successful validation, the offer is published live in the marketplace.
1. Post publishing, link the live SaaS offer to your Teams app and publish the subscription to Teams Store.

:::image type="content" source="../../../../assets/images/saas-offer/go-live-publish.png" alt-text="Screenshot shows the Go live and offer publishing phase.":::

For more information on validation and certification, check [review and publish offers](/partner-center/marketplace/review-publish-offer).

## Configure SaaS offer to your app

For the users to view your subscription plan in Teams Store, link the published SaaS offer from Partner Center to your app. There are two ways you can link the SaaS offer to your Teams app.

* Teams Developer Portal
* App manifest update

> [!NOTE]
> You need the publisher ID and offer ID from Partner Center to configure the SaaS offer to your app.

To configure from Teams Developer Portal, follow these steps:

1. Go to **Developer Portal** and select **Apps**.
1. On the **Apps** page, select the app you're linking the SaaS offer to.
1. Go to the **Plans and pricing** page and specify your publisher ID and offer ID.
1. Select **View** to preview your SaaS offer's subscription plans.
1. If everything looks good, select **Save**.

To configure through app manifest:

Update the `subscriptionOffer` property in your app manifest.

   ```json
      "subscriptionOffer": {
        "offerId": "publisherId.offerId"  
        }
   ```

> [!NOTE]
> The `subscriptionOffer` property is supported in manifest schema version 1.10 or later.

For more information to map the paid functionality to your offer and publish, see [Map your Teams app](https://aka.ms/TMTG).

## Publish your app

After linking the offer to your app, you can submit your monetized app through Partner Center to validate and publish. Perform the following prevalidation checks before submission:

* Ensure your app adheres to the [store validation guidelines](teams-store-validation-guidelines.md).
* [Prepare for store submission](submission-checklist.md).
* [Perform the required prechecks](../publish.md).
* [Submit app for validation](/office/dev/store/add-in-submission-guide).

> [!IMPORTANT]
>
> * Even if your app is already listed on the Teams Store, you must still go through the store validation process again to include your SaaS offer.
> * Flat rate offers created without the offer ID and publisher ID in the app manifest should be updated and resubmitted for validation.

After the SaaS app is published, users can view the **Buy a subscription** option in the app details dialog when the user adds your app to Teams.

:::image type="content" source="~/assets/images/saas-offer/buysubscriptionplan.png" alt-text="Screenshot shows buying the subscription for the selected app.":::

SaaS app with suitable offers is available in the Teams Store and the marketplace to purchase subscriptions.

### Post purchase

* Upon successful subscription purchase, the user is redirected to the app landing page for subscription activation. To check the existing experience for user purchase, see [monetized apps in Teams](https://aka.ms/TMTG).

* After the user activates the subscription purchase on the landing page, the user is redirected to the subscription page in Teams via a [redirect URL](https://teams.microsoft.com/_#/subscriptionManagement) that the user selects on the publisher landing page.

* Microsoft manages licenses on your behalf if you opted for the same during offer configuration. After the subscription activation, the user is redirected from the landing page to Teams license management. For more information, see [manage app licenses](end-user-purchase-experience.md#license-management).

## Remove a SaaS offer from your app

If you decide to unlink your SaaS offer from the app, follow these steps:

1. Sign in to [Developer Portal](https://dev.teams.microsoft.com/) and select **Apps**.
1. On the **Apps** page, select the app to remove the offer.
1. Go to the **Plans and pricing** page and select **Revert**.

After unlinking the offer, perform the following steps to update your Teams Store listing:

1. Select **Distribute** > **Publish to the Teams Store**.
1. Select **Open Partner Center** to begin the process of republishing your app without the offer.

If you unlink a SaaS offer included in your Teams Store listing, you must republish your app to see the change in the Teams Store.

## See also

* [Submit your app](/partner-center/marketplace/add-in-submission-guide?toc=%2Fmicrosoftteams%2Fplatform%2Ftoc.json&bc=%2Fmicrosoftteams%2Fplatform%2Fbreadcrumb%2Ftoc.json)
* [Maintaining and supporting your published app](../post-publish/overview.md)
* [Purchase and manage subscriptions and licenses](end-user-purchase-experience.md)
* [Validation guidelines for apps linked to SaaS offer](teams-store-validation-guidelines.md#apps-linked-to-saas-offer)

