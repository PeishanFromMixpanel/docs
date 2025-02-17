---
title: "Plan Your Implementation"
slug: "plan-your-implementation"
hidden: false
metadata: 
  title: "Mixpanel Implementation | Mixpanel Developer Docs"
createdAt: "2021-04-29T19:12:41.293Z"
updatedAt: "2023-03-26T23:45:51.525Z"
---
Implementing a new tool can be daunting, but it doesn’t have to be. You can implement Mixpanel in a few different ways to ensure it fits with the rest of your tech stack seamlessly.

# Already Collect Data With a CDP or In-House Tools?
### Customer Data Platform (CDP)
If you already send events to a CDP like [Segment](https://segment.com/docs/connections/destinations/catalog/actions-mixpanel/) or [Rudderstack](https://rudderstack.com/integration/mixpanel/), you can get up and running with Mixpanel in seconds.

### Reverse ETL
If you want a more out-of-the-box solution to load data from your warehouse, Mixpanel also connects to a variety of Reverse ETL tools including [Census](https://docs.getcensus.com/destinations/mixpanel) and [Hightouch](https://hightouch.io/docs/destinations/mixpanel/). These make it easy to route data from your warehouse to Mixpanel and all other tools in your stack.

### Cloud
If you already collect events with your own internal systems, see our [Amazon S3](doc:s3-import) and [Google Cloud Storage](doc:gcs-import) guides to reliably load these events into Mixpanel.

# Need To Start Tracking Product Data?
It takes less than 5 minutes to track an event to Mixpanel with our Javascript, server, or mobile SDKs. There are two general approaches when it comes to tracking with our SDKs:

* **Server-Side (Recommended):** In this method, you send events from your servers to Mixpanel. This approach is the most reliable and easy to maintain, since it lives in an environment that you control. It also means that you can add tracking in one place (your servers) rather than in 3 places (web, iOS, Android), which keeps tracking unified and clean. See our [quickstart](doc:server) and [best practices](doc:effective-server-side-tracking) for more details on effective server-side tracking.

* **Client-Side:** In this method, events are generated on the client device and sent to the Mixpanel API. There are two types of client-side tracking: web (Javascript) and mobile. This can be faster to set up, but is the least reliable form of tracking due to ad-blockers. It's also harder to update tracking, since the environment where the tracking code runs is out of your control (web or mobile clients). You can improve reliability of client-side tracking using a [proxy](doc:collection-via-a-proxy), but this takes more effort.

In general, we recommend tracking everything you possibly via your servers, and only supplementing that with client-side tracking when necessary.

# What To Track
If you’re just starting to track data, we suggest starting simple by tracking two events critical to your product.

> 📘
> Not sure what an event or property is? Check out [What is Mixpanel](doc:what-is-mixpanel) to get a quick introduction to these important concepts.

## Sign Up Event
This is the event where a user makes themselves known to your product by “creating an account”. We recommend tracking Sign Up because it's a quick and easy way to get real insights on your product’s growth.

You can do this with a simple code snippet:
```javascript
mixpanel.track("Sign Up")
```
Tracking a sign up event can let you answer simple but key questions like:

:seedling: **What is our growth? How many people are signing up on our website (daily, monthly, etc.)?**

Mixpanel also lets you augment this data with event properties, like a referral source, or if the user opted out of emails.

You can add tracked properties to the code by labeling each event property and assigning it a value in the code snippet, like in this example:
```javascript
mixpanel.track('Sign Up', {
	'source': "Pat's affiliate site",
	'Opted out of email': true,
});
```
This can help you answer even deeper questions like:

:calling: **Which platform are most of our customers signing up on? **
:inbox-tray: **What channels are generating new sign ups most effectively?**

## Value Moment Event
A value moment is a key user action that indicates that a user is able to generate or realize value in your product, and is often a strong predictor of healthy user engagement and retention.

The value moment event should be tailored for your specific product. For a social product it's _creating a post_, for a streaming platform it's _completing a TV series_, for an e-commerce site it could be _completing a purchase_.

Here’s an example snippet that includes both a value moment event ‘Purchased Item’ and properties 'Item Type' and 'Price':
```javascript
mixpanel.track('Purchased Item', {
  'Item Type': 'Coffee',
  'Price': 2.50,
});
```
Tracking a value moment can help answer questions like:

:star2: **What does active engagement look like? How many users are experiencing value in my product?**
:revolving-hearts: **What is our retention? How many people are coming back to realize value in our product?**
:moneybag: **What is our activation rate? How many people who sign up make it to the Value Moment?**

> 📘See Your Events in Action
> Once you've implemented your signup and value moment events, try the [Company KPIs template](https://mixpanel.com/project?show-event-translator=true) to turn your two events into nine unique reports with only a few simple clicks.

From here, you can gradually start tracking more events to better understand user behavior in your app.
