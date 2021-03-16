

# HOW TO use guest access to the Datablase

If you're somewhat able to write an SQL query, and would like to find out some complex information about historical statistics, Guest Access To The Datablase™ might be for you!

The guest account is limited to *reading* data only so you can't break anything, and it's limited to 10 seconds per query so you can't accidentally lock everybody else out with a whoopsie.

*(If you need a longer timeout, contact us in `#datablase` on the SIBR Discord)*

## Login to pgAdmin

Visit https://pgadmin.sibr.dev/ and log in with username **guest@sibr.dev** and password **salmon**

![Image of login screen for pgAdmin](login.png)

## Find the latest database

First, expand the **Servers** to see the available servers known to this account.
![](pgadmin-1.png)

The SIBR Datablase server should already be in the list. If not, see the **Adding the SIBR server** section below.

Within the SIBR server you'll find several databases - one called **postgres** which is the default and not used by Datablase operations, and one or more named **blaseball-X.Y.Z**.

![](pgadmin-2.png)

You should always choose the *highest version number* database - it'll have the freshest, crispiest data from the current season.

## Get to the query tool

To start making queries, simply right-click the database and choose **Query Tool...**

![](pgadmin-3.png)

You've now found your home - the pgAdmin Query Tool! Though intimidating at first, you'll come to know and love every nook and cranny of this homey spot.

![](pgadmin-4.png)

Simply type a valid SQL query in the top box and hit **F5** to execute and see the results at the bottom!

## An Example

Let's say you want to see all the records of home runs hit by noted Steaks phenom **Zephyr McCloud** during their debut in season 14!

    SELECT * from data.game_events
    WHERE batter_id='41bdb527-1fb2-487d-8237-093958e737e4'
    AND event_type='HOME_RUN'
    AND season=13

*Pro tip: Blasebot's `bb!player` command is great for finding player IDs!*

![](pgadmin-5.png)

Voila! You've run your first query and gotten some results!
You can download your results with the **Download as CSV/TXT** button marked above, or just copy and paste things you need from the query results.

## Datablase Structure

TODO... for now, please ask in the `#datablase` channel on the SIBR Discord for help deciphering what all these crazy tables and views are.

## Next Steps

The Datablase is a PostgreSQL database, a long-running and stable technology with *lots* of tutorials and help documentation available. If you study up on how to construct queries you'll be doing complex stuffin no time!

And then if you get really good you can take over this project from us!

## Appendix: Adding the SIBR Server

Please contact `@lilserf#8712` on the SIBR Discord for instructions, as this article is long enough already.