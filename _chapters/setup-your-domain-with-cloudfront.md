---
layout: post
title: Set up Your Domain with CloudFront
date: 2017-02-09 00:00:00
description: Tutorial on how to point your domain to a CloudFront Distribution using AWS Route 53.
---

Now that we have our CloudFront distribution live, let's set up our domain with it. You can purchase a domain right from the [AWS Console](https://console.aws.amazon.com) by heading to the Route 53 section in the list of services.

![Select Route 53 service screenshot]({{ site.url }}/assets/select-route-53-service.png)

### Purchase a Domain with Route 53

Type in your domain in the **Register domain** section and click **Check**.

![Search available domain screenshot]({{ site.url }}/assets/search-available-domain.png)

After checking it's availability, click **Add to cart**.

![Add domain to cart screenshot]({{ site.url }}/assets/add-domain-to-cart.png)

And hit **Continue** at the bottom of the page.

![Continue to contact details screenshot]({{ site.url }}/assets/continue-to-contact-detials.png)

Fill in your contact details and hit **Continue** once again.

![Continue to confirm details screenshot]({{ site.url }}/assets/continue-to-confirm-detials.png)

Finally, review your details and confirm the purchase by hitting **Complete Purchase**.

![Confirm domain purchase screenshot]({{ site.url }}/assets/confirm-domain-purchase.png)

Next, we'll add an alternate domain name for our CloudFront Distribution.

### Add Alternate Domain for CloudFront Distribution

Head over to the details of your CloudFront Distribution and hit **Edit**.

![Edit CloudFront Distribution screenshot]({{ site.url }}/assets/edit-cloudfront-distribution.png)

And type in your new domain name in the **Alternate Domain Names (CNAMEs)** field.

![Set alternate domain name screenshot]({{ site.url }}/assets/set-alternate-domain-name.png)

Scroll down and hit **Yes, Edit** to save the changes.

![Yes edit CloudFront changes screenshot]({{ site.url }}/assets/yes-edit-cloudfront-changes.png)

Next, let's point our domain to the CloudFront Distribution.

### Point Domain to CloudFront Distribution

Head back into Route 53 and hit the **Hosted Zones** button.

![Select Route 53 hosted zones screenshot]({{ site.url }}/assets/select-route-53-hosted-zones.png)

Select your domain from the list and hit **Create Record Set** in the details screen.

![Select create record set screenshot]({{ site.url }}/assets/select-create-record-set.png)

Leave the **Name** field empty since we are going to point our bare domain (without the www.) to our CloudFront Distribution.

![Leave name field empty screenshot]({{ site.url }}/assets/leave-name-field-empty.png)

And select **Alias** as **Yes** since we are going to simply point this to our CloudFront domain.

![Set Alias to yes screenshot]({{ site.url }}/assets/set-alias-to-yes.png)

In the **Alias Target** dropdown, select your CloudFront Distribution.

![Select your CloudFront Distribution screenshot]({{ site.url }}/assets/select-your-cloudfront-distribution.png)

Finally, hit **Create** to add your new record set.

![Select create to add record set  screenshot]({{ site.url }}/assets/select-create-to-add-record-set.png)

It can take around an hour to update the DNS records but once it's done, you should be able to access your app through your domain.

![App live on new domain screenshot]({{ site.url }}/assets/app-live-on-new-domain.png)

Next up, we'll take a quick look at ensuring that our www. domain also directs to our app.
