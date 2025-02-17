---
title: "Signal"
slug: "signal"
hidden: false
metadata:
  title: "Signal"
  description: "Learn about Mixpanel Signal report."
---

# Signal Report

Signal measures the association between a correlation event and a goal event and quantifies the correlation between the two. This facilitates a deeper understanding of the behaviors that drive customer conversions, and can help guide product decisions.

Note: There are now more features available in Signal that are not highlighted in the video below. Refer [here](https://help.mixpanel.com/hc/en-us/articles/115004567503-Signal-Report#build-a-query-in-signal) to get current information on how to build Signal queries.

![https://embed-ssl.wistia.com/deliveries/e16fc49b56e773a413011bb57142aa9701e481b6.webp?image_crop_resized=960x540](https://embed-ssl.wistia.com/deliveries/e16fc49b56e773a413011bb57142aa9701e481b6.webp?image_crop_resized=960x540)

## Signal Use Case

Using an a music sharing application as an example can highlight the value of quantifying correlations between events.

The music sharing app may want to understand the correlation between top events and users who purchase a song on the app. It is important to understand what the optimal actions that users take before purchasing a song are.

Building this query in Signal would involve selecting the target users, and how the "Song Purchased" goal event is correlated with the top events.

![https://help.mixpanel.com/hc/article_attachments/360054782491/mceclip0.png](https://help.mixpanel.com/hc/article_attachments/360054782491/mceclip0.png)

Values are returned after running the correlation. “Song Played” could have a strong positive correlation with purchasing a song. Most of the users who played a song later purchased a song.

![https://help.mixpanel.com/hc/article_attachments/360054664292/Screen_Shot_2018-07-13_at_9.19.24_AM.png](https://help.mixpanel.com/hc/article_attachments/360054664292/Screen_Shot_2018-07-13_at_9.19.24_AM.png)

This information can be used in future product decisions. By knowing that those who play songs are more likely to purchase songs, it is possible to build tools to encourage song plays. This could lead to a dramatic increase in the amount of users purchasing songs.

## Build a Query in Signal

By default, Mixpanel will build a query to show how your [top 50 events](https://help.mixpanel.com/hc/en-us/articles/360001360643-Top-Events-in-Reports) correlate with 2nd week retention in the last quarter for all users. This translates to, “How do the top events correlate with two week retention in the last quarter for all users?"

![https://help.mixpanel.com/hc/article_attachments/7777682199956/Screen_Shot_2022-07-13_at_10.13.57_PM.png](https://help.mixpanel.com/hc/article_attachments/7777682199956/Screen_Shot_2022-07-13_at_10.13.57_PM.png)

To build a new query with Signal, enter the Signal report in the desired Mixpanel project.

Signal queries require a minimum of 60 days worth of data. Queries with any less data history will return a calculation error.Signal currently supports filtering only by event properties. Custom events with profile property filters will now be shown in the event dropdown.

1. Determine and specify the target users. “All users” is the default.

![https://help.mixpanel.com/hc/article_attachments/7777681516180/Screen_Shot_2022-07-13_at_10.13.57_PM.png](https://help.mixpanel.com/hc/article_attachments/7777681516180/Screen_Shot_2022-07-13_at_10.13.57_PM.png)

2. Select any event performed by the target user by clicking the **+** sign.

![https://help.mixpanel.com/hc/article_attachments/7777750405268/Screen_Shot_2022-07-13_at_10.13.57_PM_copy.png](https://help.mixpanel.com/hc/article_attachments/7777750405268/Screen_Shot_2022-07-13_at_10.13.57_PM_copy.png)

3. Further filter by property by clicking **+ Filter** and selecting any properties as well as the frequency of occurrence.

![https://help.mixpanel.com/hc/article_attachments/7777752285204/Screen_Shot_2022-07-13_at_10.19.21_PM.png](https://help.mixpanel.com/hc/article_attachments/7777752285204/Screen_Shot_2022-07-13_at_10.19.21_PM.png)

4. Determine and select the Goal Event and its properties. The goal event can be a specific event with a frequency (users did Goal Event at least x number of times) or one of the default Signal retention events calculated by Mixpanel.

![https://help.mixpanel.com/hc/article_attachments/7777768697236/Screen_Shot_2022-07-13_at_10.20.49_PM.png](https://help.mixpanel.com/hc/article_attachments/7777768697236/Screen_Shot_2022-07-13_at_10.20.49_PM.png)

The default retention events available in Signal include:

- 2nd week retention: Users doing a specific action or set of actions in your project and then returning to do anything within two weeks.
- 3rd week retention: Users doing a specific action or set of actions in your project and then returning to do anything within three weeks.
- 4th week retention: Users doing a specific action or set of actions in your project and then returning to do anything within four weeks.
- 2nd month retention: Users doing a specific action or set of actions in your project and then returning to do anything within two months.

5. Determine and select the Correlation Event and its properties. It is possible to add up to ten different correlation events by clicking the **+** button at the bottom of the query builder.

- The correlation event can be [broken down by property](https://help.mixpanel.com/hc/en-us/articles/115004582086#breakdown-a-query). To do this, select **+ Breakdown** and select the property to break the data down by.
- The correlation event can be [filtered by property](https://help.mixpanel.com/hc/en-us/articles/115004582086#filter-a-query). To do this, select **+ Filter** and select the property and property value you want to filter by.

![https://help.mixpanel.com/hc/article_attachments/7777773378580/Screen_Shot_2022-07-13_at_10.22.08_PM.png](https://help.mixpanel.com/hc/article_attachments/7777773378580/Screen_Shot_2022-07-13_at_10.22.08_PM.png)

6. Select the time frame for the query and the users who are to be evaluated. It’s important to select a long enough time frame that allows users to complete both the correlation event(s) and the goal event.

![https://help.mixpanel.com/hc/article_attachments/7777794074004/Screen_Shot_2022-07-13_at_10.24.59_PM.png](https://help.mixpanel.com/hc/article_attachments/7777794074004/Screen_Shot_2022-07-13_at_10.24.59_PM.png)

6. Click **Correlate**.

![https://help.mixpanel.com/hc/article_attachments/7777774565268/Screen_Shot_2022-07-13_at_10.22.08_PM.png](https://help.mixpanel.com/hc/article_attachments/7777774565268/Screen_Shot_2022-07-13_at_10.22.08_PM.png)

## Difference Between New Users and All Users

New users are users who have completed their first event in the selected time frame.

All users will look at all users in your Mixpanel project who have completed the event in the selected time frame.

## Breakdown a Query

It is possible to breakdown the correlation event of a Signal query by its properties. Breaking down the query will return results for all of the values tied to the breakdown property.

There are two different requirements that must be met in order to break down a Signal query.

- The target users must be “All users” and not “New users”.
- A query can only be broken down if one correlation event is selected.

![https://help.mixpanel.com/hc/article_attachments/7777796323348/Breakdown1.gif](https://help.mixpanel.com/hc/article_attachments/7777796323348/Breakdown1.gif)

## Filter a Query

It is possible to filter the correlation event of a signal query by a property value. Filtering the query will return results for only the property value that the query is filtered by.

![https://help.mixpanel.com/hc/article_attachments/7777796228500/FilterHigh.gif](https://help.mixpanel.com/hc/article_attachments/7777796228500/FilterHigh.gif)

## Use a Cohort as the Target Users

It is possible to select [a cohort](https://help.mixpanel.com/hc/en-us/articles/115005708186-Cohorts-Overview-) as the target users in a Signal query. This runs Signal calculations, such as correlation and opportunity, with the queried population being all users **currently** in the cohort.

To build a Signal query with a cohort as the target users, enter the Signal report, select the **users** dropdown, and select a cohort from the list. [Learn how to create a cohort.](https://help.mixpanel.com/hc/en-us/articles/115005701343-Create-Cohorts)

![https://help.mixpanel.com/hc/article_attachments/7777798950292/Signalsection1.gif](https://help.mixpanel.com/hc/article_attachments/7777798950292/Signalsection1.gif)

## Use a Cohort as The Goal Event

It is possible to select [a cohort](https://help.mixpanel.com/hc/en-us/articles/115005708186-Cohorts-Overview-) as the goal condition of a Signal query. This runs Signal calculations, such as correlation and opportunity, with the the goal being target users either existing in or not existing in the selected cohort.

To build a Signal query with a cohort as the goal event, select the **Goal Event** dropdown, select the **Cohorts** tab, and select a cohort. [Learn how to create a cohort.](https://help.mixpanel.com/hc/en-us/articles/115005701343-Create-Cohorts)

![https://help.mixpanel.com/hc/article_attachments/7777813994388/Signalsection2.gif](https://help.mixpanel.com/hc/article_attachments/7777813994388/Signalsection2.gif)

**[Cohorts are always calculated at query time.](https://help.mixpanel.com/hc/en-us/articles/115005708186-Cohorts-Overview-#cohorts-characteristics)**

This means that if a “from date” and “to date” are selected so that the query is analyzing a time period in the past, the cohort will NOT be the cohort during that historical time period. The cohort will be current, meaning the users analyzed will be the users **currently** in the cohort.

## Interpreting Results

## Summary View

Each correlation will be represented by one card in the summary view results. The list-view will display the optimal action, correlation with the goal event, and key findings about the event. Results can be sorted by correlation strength or by Mixpanel opportunity score.

![https://help.mixpanel.com/hc/article_attachments/7777816143508/Screen_Shot_2022-07-13_at_10.32.35_PM.png](https://help.mixpanel.com/hc/article_attachments/7777816143508/Screen_Shot_2022-07-13_at_10.32.35_PM.png)

## Scores

By default, the results will be sorted by Opportunity. “Opportunity” is Mixpanel’s proprietary calculation of how important a given correlation might be. The correlation strength is calculated using the phi coefficient. [Reference here](https://help.mixpanel.com/hc/en-us/articles/115004567503-Signal-Report#signal-machine-learning-model) for more detail on how Opportunity and correlation strength is calculated.

## Key Findings

The key findings presented are rarity analysis results and conversion measurements. Rarity defines how common or uncommon it is for users to complete an individual event. The conversion measurements qualifies how likely a given conversion is to be helpful.

**Rarity Analysis** can be broken down into:

- Rare in user group.
- Never performed in user group.
- Uncommon in user group.
- Common in user group.
- Majority of user group performed.

**Conversion Measures** can be broken down into:

- No users converted to goal.
- Unlikely to be useful.
- Associated almost perfectly with not converting.
- Associated almost perfectly with converting.

## Detailed view

To access the detailed view, click on a card in the summary view.

![https://help.mixpanel.com/hc/article_attachments/7777852474516/Screen_Shot_2022-07-13_at_10.33.37_PM.png](https://help.mixpanel.com/hc/article_attachments/7777852474516/Screen_Shot_2022-07-13_at_10.33.37_PM.png)

The detailed view provides the correlation calculations for each event evaluated. This view uses a heat map to show the strength of the correlation with the goal event.

The x-axis represents the velocity, or the number of days it took users to complete the event (up to 15 days) and the y-axis shows the frequency of the event, or the number of times the event was done, up to ten times.

![https://help.mixpanel.com/hc/article_attachments/7777852993556/DetailedView.png](https://help.mixpanel.com/hc/article_attachments/7777852993556/DetailedView.png)

## Optimal Action

The optimal action will be highlighted in green on the heat map.

The optimal action tells you how many times and in how many days your customers should do the event in order to achieve your optimal correlation. Frequency labels are listed below the action and provide precise information, based on the correlation, about when your users should complete the event. For example, if you are a music streaming app and wanted to see how a “Play Song” event correlates with two week retention, you might see something like, “Play song once within ten days” as an optimal action.

## Supporting Statistics

For each combination Mixpanel will provide supporting statistics for further analysis:

- **Precision**: Percent of users who convert to your goal among those who did this event at least x times within y days.
- **False omission rate**: Percent of users who convert to your goal among those who did this event fewer than x times within y days.
- **Recall**: Percent of converted users who did this event at least x times within y days.
- **Fall-out**: Percent of unconverted users who did this event at least x times within y days.
- **Correlation**: Association between performing this event at least x times in y days and converting to your goal.

![https://help.mixpanel.com/hc/article_attachments/7777869737492/Screen_Shot_2022-07-13_at_10.35.27_PM.png](https://help.mixpanel.com/hc/article_attachments/7777869737492/Screen_Shot_2022-07-13_at_10.35.27_PM.png)

To see the calculations of the optimal correlation data, hover of the ƒx in the upper right-hand corner of the chart at the bottom of the heat map.

![https://help.mixpanel.com/hc/article_attachments/7777869737748/Screen_Shot_2022-07-13_at_10.35.35_PM.png](https://help.mixpanel.com/hc/article_attachments/7777869737748/Screen_Shot_2022-07-13_at_10.35.35_PM.png)

## Signal Machine Learning Model

Signal calculates correlation using a well-known statistical algorithm called the phi coefficient. In addition to correlation, Mixpanel calculates what is called an opportunity score, and also presents a list of key findings.

## Correlation

The phi coefficient is a single number between -1 and 1 and it indicates how closely an event moves with your goal event. 1 means that 100% of all users that did the goal event also did the correlation event. -1 means that 0% of users that did the goal event also did the correlation event.

## Opportunity Score

“Opportunity” is Mixpanel’s proprietary calculation of how important a given correlation might be. Opportunity helps pare down results by eliminating false positives and highlighting weak correlations that may be actionable. Based on this assessment, which determines how much an event impacts conversion on your goal, Mixpanel will tell you if there is an opening to make a change in your product or not.

Once we have the correlation, the results on the summary page will display the optimal action, correlation with the goal event, and our key findings about that optimal action.

The optimal action tells you how many times and in how many days your customers should do the event in order to achieve your optimal correlation. Frequency labels are listed below the action and provide precise information, based on the correlation, about when your users should complete the event. For example, if you are a music streaming app and wanted to see how a “Play Song” event correlates with two week retention, you might see something like, “Play song once within ten days” as an optimal action.

**Frequency Labels** -- \*these will be supplemented with temporal labels, i.e. At least 4 times in 10 days.\*

- Many times
- Just once
- At least x times
- Always avoid
- As few times as possible
- No strong correlations found
- Is complex

The correlation with the goal event presents to you the optimal correlation for the event and tells you whether this indicates a strong or weak association with your goal. We calculate the association using a well-known statistical measure called the phi coefficient. The phi coefficient is a single number between -1 and 1 that indicates how closely an event moves with your goal event.

Finally, we will display the key findings. The key findings contain the rarity analyses and the impact to conversion. The rarity analyses define how common or uncommon is it for users in your user group to complete your event and the impact to conversion explains how the event impacts conversion to your Goal event (i.e. retention). These help you interpret the correlations. A certain event may have strong correlation to a goal event but may not have been completed by many users in your group and thus is unlikely to be useful. Below we have listed the different messages you can see as a part of the rarity analysis and the impact to conversion.

**Rarity Analyses**

- Rare in user group
- Never performed in user group
- Uncommon in user group
- Common in user group
- Majority of user group performed

**Conversion Measures**

No users converted to goal.

- Example: None of the users analyzed converted to the goal in question.

Unlikely to be useful.

- Example: There may be no correlation (positive or negative) between the two events.

Associated almost perfectly with not converting. Something might be off here.

- Example: Users who trigger an “uninstall” event are not going to complete your Goal event.

Associated almost perfectly with . Too good to be true?

- Example: Users who trigger a purchase event will always trigger an add to cart event. Add to cart and purchase will always have high correlation.

## Key Findings

Signal also presents two key findings, rarity analysis results and conversion measurements. Rarity defines how common or uncommon it is for users to complete an individual event. The conversion measurements qualifies how likely a given conversion is to be helpful. For example, if all users are converting because the application forces this by design, then the conversion measurement will flag this as "unlikely to be useful".

## Signal CSV Download Glossary

Below are explanations for the summary statistics that you will find in the CSV download of your Signal correlation. To download the results to a CSV, click the **Download CSV** icon in the upper right hand corner of the Summary Results view or the Detailed Results view after you have run your correlation.

![https://help.mixpanel.com/hc/article_attachments/7777872257684/Screen_Shot_2022-07-13_at_10.37.09_PM.png](https://help.mixpanel.com/hc/article_attachments/7777872257684/Screen_Shot_2022-07-13_at_10.37.09_PM.png)

- **Frequency:** Number of times, up to 10, a user should complete the event for the correlation.
- **Intervals:** Number of days, up to 15, when a user should complete the event for the correlation.
- **True positive:** Number of positive correlations that are correctly identified.
- **True negative:** Number of negative correlations that are correctly identified.
- **False positive:** Number of positive correlations that are incorrectly identified.
- **False negative:** Number of negative correlations that are incorrectly identified.
- **Correlation:** The association between your event to your goal event.
- **Precision:** Percent of users who convert to your goal among those who did this event at least x times within y days
- **Fall-out:** Percent of unconverted users who did this event at least x times within y days.
- **Recall:** Percent of converted users who did this event at least x times within y days.
- **False Omission Rate:** Percent of users who convert to your goal among those who did this event fewer than x times within y days.
- **Phi max:** Single number between -1 and 1 that indicates how closely an event moves with your goal event. 1 means that 100% of all users that did your goal event also did the event you are evaluating. -1 means the opposite: 0% of users that did you goal event also did the event you are evaluating.
- **Mixpanel Opportunity Score:** Mixpanel’s proprietary calculation of how important a given correlation might be.


