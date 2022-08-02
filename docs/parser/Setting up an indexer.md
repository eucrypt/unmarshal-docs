# Setting Up your own Indexer Using Unmarshal Parser

![setup-your-indexer.png](../../images/parser/setup-your-indexer.png)


To start with, you will need to head to [Unmarshal's Unified Console](https://console.unmarshal.io/).


**1.  Login/Create an account**

To use the <Project Name>, you will need an Unmarshal account. The account is free to create and lends you access to Unmarshal's world class APIs across over 7 chains.

**2.  Click on the Parser Tab** on the sidebar to your left. Click on "Create New"

![](https://lh6.googleusercontent.com/vIQm8n3zoN2w4TPd82MpeUyqLAoPFSpERrOOmRzKxaAnhGnJBei5tm6_gKIetuIRGHI_k-DsXnjBd5s9lorgOIQ2bqQi6o-xQmjH-1XpK4ovWRd5Gs7olGY-yCSgryTGt8s9quEmcXIrCgZNbqbS6Bk)

**3.**  Select **"Deploy and Maintain"** to Deploy an indexer

![](https://lh4.googleusercontent.com/8Lc5oN7Gt_qU2NKYWi7l5ppecoB687X19LG4E8LD_NZIziCxc_k_j0pl9QIAqepGEhu6ozzou2OhWcpffa3Yiwoc12sigvblS9F051SlSONm9jmfb8xj_u4tlpftvUKPk3vX7ehD4gjpY0ZxEPgxcoc)

**4.  Select the chain** your contract is deployed on. We support a generous number of EVM based chains including testnets.

![](https://lh6.googleusercontent.com/zPlyQ9wtgg7gIwC1eufe4ujICSElyY2DBhyUKY_Se0luEcuVI0ApR7t48SmAjkITyoU0hbaV2GMrYrtjII-y483k75S6ccL-mHDL7mb8lFTdf7sR7V-DSzlP2tWf2V8WGCFtaArz7Hniuw7jAon_VNA)

**5.  Contract Address**

Paste in your contract's address here.

![](https://lh5.googleusercontent.com/Vr3798d7-WOyNeXgaHAQVWAepm0F_NE9kyTvWdN5Ef-nV7e2bG4pCleRkZ9BeareLRmvgEL61XVI7r0JLJPBKMub3XHJ4tHAbVbxsIkJAIs-6E0UiD_8qagivANySOxy9wdp1J45S7Tpbbf_JsextRY)

**6.  Fetching ABI**

The ABI is a JSON<ref> that holds the available list of functions and events in a contract that can be accessed and their respective signatures. The form will auto-fetch a verified ABI from the official scan if available. You are also free to paste in the ABI of the contract if you wish to.

![](https://lh5.googleusercontent.com/qeAHId-qGtAilfVsBKYzdJASYaMgKOGk166veeRVhxLC9TfvelCMwk9sY34RhscQSAxMNPjQtfSaBSk31KqUm7WJnmHuMDgtdSmzS7_wYsJivPU82TRc4ET_cxSUclFroxdnJL_fiHVN5PvP3rmuX8o)

**7.  Events/Functions**

Pick the events or functions you are interested in indexing or monitoring. Indexing functions cost API credits and we currently do not index in internal transactions.

![](https://lh5.googleusercontent.com/fKzVKyfirn4CmM2jh7J35NyXle-O0sFMbrFYRzRh5rq_DEnX3Lin71fu8JNSsLrv0kP044vtr1xzIS_3nRrrSydu7CBbvsD6iZ5QFnGiJVf-asFglo4YdYYn0kVTKCkgStPLNq7B-xolY9dJqb2wzEc)

![](https://lh6.googleusercontent.com/-QrO83OBtG_f2cM-jMVmqVHvrsbINASPDjH4mZYh-yOTVzBYTZZwG7NvVXVKt-6fsl7bs85RxUGC-ZotywdOpHCZ8dco8evS6AMF1sp1T0Uhu22P3LowDlALlFM3wzssrMj8ymdKrM7gPn4ZaNOaS_Q)

**8.  Start Block**

This item tells your parser the block number to start indexing from. If available, it points by default to the block number your contract was deployed at.

You are also free to enter a custom start block. The later your start block is, the faster the parser will be in sync with the chain at the cost of excluding transactions from older blocks.

You could also enter a block in the future to begin indexing from. (Bear in mind that the parser will lag behind the node by 10 blocks. This ensures, that all the transactions whose data is indexed are part of the canonical chain without the user having to worry about chain re-orgs)

![](https://lh3.googleusercontent.com/5mDdrtjLggNYWDd1LA1AAkFclSSMeSd_3zbmGcIgrZ4uSOcwjzkxgP9KWvWhH3dOlN05z6xQsR28qBz40e2M3rTD6zVpfmZh4jjqaqSfnOpf2cwkPgU9Yh9_ulULHqtSXaynCrh-CYnrkklApzg-KXE)

**9.  Parser details for your reference**

Name your parser. This will help you identify and more clearly differentiate between multiple parsers.

![](https://lh6.googleusercontent.com/q-WeKGAw3eiSfdCD4ynPgF2E0A-upklDVHh64SoLxNcba4WIwqeaIQwOnzdAYKTCdA8uJx-7d4ONeCf9DB8qIQDb-UpaxsOwFefZ6P5B1IWU2tNTAmnbLMnZAK-ifDVD0DeliNeCcwIaSi4SZXZDMwI)

**10.  Schema Name**
Pick a schema name for your parser. If you wish, you could reuse a schema name across multiple parsers as long as each is indexing a different contract.

You could also have multiple parsers indexing the same contract as long as they use different schemas.

![](https://lh3.googleusercontent.com/XTawZ_DSpflUEY1B98zzynufmNqdK6YjajMo-qx7E2QJjJ-Le7glyrxNKjekWGHYfgtNifBllzS6iqp-r_HyflR7_frwImOKd25cynVrnyjuIow80k4BMtMcaawpNLiRfuGk2ZoKkk5OWflDIRvWaw8)

**Submit your request!**

Et voilà, your parser is up and running!! No worrying about instances or compute units, manifests or any of that technical gobbledygook.

![](https://lh6.googleusercontent.com/63m6PMTxbIYmc3ekLj0U2ndd8T_Ikjf-qsnU7hEkiVS_ZXCTXzFYFUfdwBuHjtwqMXlTHyjyvOWhpAAyxH7ys9j5VUlMH6GEPoghaHts28SjadoXmfZV1f3IAd0cEK2A_AGR1Y14POBRLCfBVqt0QSA)

Now that you have a parser running and in-sync, you might be wondering how you gain access to that data? Unmarshal provides you with two easy ways to either visualise or query all that data.

# Accessing your data

The Parser provides two ways of accessing the data that you have indexed.

## Metabase

**What exactly is it?**

Metabase is analogous to a GUI for a Database that gives you full access to your data. Apart from the ability to see data in a tabulate format, it allows you to run SQL queries to access your data. It also provides you with the ability to create dashboards like the one [here](https://stake.unmarshal.io/analytics/493a7f3a-c151-47db-92ca-4fbe8dd7e4e5), created for Unmarshal's very own [staking platform](https://stake.unmarshal.io/).


You can read more about Metabase [here](https://www.metabase.com/learn/getting-started/getting-started.html).

**Who is it for?**

Metabase is a powerful tool for visualising on-chain protocol data which can be used by researchers, dApps, and investors for data analytics.

Check out our [webinar](https://www.youtube.com/watch?v=owtdrGFtj5c&t=3s) to understand how dApp analytics can be used to improve application performance and analyse user behaviour.

**How do I access it?**

The login credentials for metabase are available on your parser tab. You can click on the "View Details" button to get the URL, Username and Password. Keep in mind that you are free to change your password after logging in, to whatever you prefer.

For more details refer to <Metabase page link>


## GraphQL

**What exactly is it?**

The service starts a GraphQL server for you with all the schemas and resolvers auto-generated. GraphQL is an easy way to access all data in your database and cherry pick what you want in your response. GraphQL is a "Query Language" that you can submit via post requests to a server that supports it. You can learn more about it [here](https://graphql.org/learn/queries/).

**Who is it for?**

With the help of GraphQL APIs, dApp builders can access on-chain data in the form of APIs that can be integrated into their applications through backend. It is a great querying tool to access highly specific, rich protocol data outside of the one provided by our standard set of Unmarshal APIs.

How do I access it?

Refer to <GraphQL page link>
Setting Up your own Indexer Using Unmarshal Parser


To start with, you will need to head to Unmarshal's Unified Console.

1. Login/Create an account

To use the , you will need an Unmarshal account. The account is free to create and lends you access to Unmarshal's world class APIs across over 7 chains.

2. Click on the Parser Tab on the sidebar to your left. Click on "Create New"



3. Select "Deploy and Maintain" to Deploy an indexer



4. Select the chain your contract is deployed on. We support a generous number of EVM based chains including testnets.



5. Contract Address

Paste in your contract's address here.



6. Fetching ABI

The ABI is a JSON that holds the available list of functions and events in a contract that can be accessed and their respective signatures. The form will auto-fetch a verified ABI from the official scan if available. You are also free to paste in the ABI of the contract if you wish to.



7. Events/Functions

Pick the events or functions you are interested in indexing or monitoring. Indexing functions cost API credits and we currently do not index in internal transactions.





8. Start Block

This item tells your parser the block number to start indexing from. If available, it points by default to the block number your contract was deployed at.

You are also free to enter a custom start block. The later your start block is, the faster the parser will be in sync with the chain at the cost of excluding transactions from older blocks.

You could also enter a block in the future to begin indexing from. (Bear in mind that the parser will lag behind the node by 10 blocks. This ensures, that all the transactions whose data is indexed are part of the canonical chain without the user having to worry about chain re-orgs)



9. Parser details for your reference

Name your parser. This will help you identify and more clearly differentiate between multiple parsers.



10. Schema Name
    Pick a schema name for your parser. If you wish, you could reuse a schema name across multiple parsers as long as each is indexing a different contract.

You could also have multiple parsers indexing the same contract as long as they use different schemas.



Submit your request!

Et voilà, your parser is up and running!! No worrying about instances or compute units, manifests or any of that technical gobbledygook.



Now that you have a parser running and in-sync, you might be wondering how you gain access to that data? Unmarshal provides you with two easy ways to either visualise or query all that data.

Accessing your data
The Parser provides two ways of accessing the data that you have indexed.

Metabase
What exactly is it?

Metabase is analogous to a GUI for a Database that gives you full access to your data. Apart from the ability to see data in a tabulate format, it allows you to run SQL queries to access your data. It also provides you with the ability to create dashboards like the one here, created for Unmarshal's very own staking platform.

You can read more about Metabase here.

Who is it for?

Metabase is a powerful tool for visualising on-chain protocol data which can be used by researchers, dApps, and investors for data analytics.

Check out our webinar to understand how dApp analytics can be used to improve application performance and analyse user behaviour.

How do I access it?

The login credentials for metabase are available on your parser tab. You can click on the "View Details" button to get the URL, Username and Password. Keep in mind that you are free to change your password after logging in, to whatever you prefer.

For more details refer to

GraphQL
What exactly is it?

The service starts a GraphQL server for you with all the schemas and resolvers auto-generated. GraphQL is an easy way to access all data in your database and cherry pick what you want in your response. GraphQL is a "Query Language" that you can submit via post requests to a server that supports it. You can learn more about it here.

Who is it for?

With the help of GraphQL APIs, dApp builders can access on-chain data in the form of APIs that can be integrated into their applications through backend. It is a great querying tool to access highly specific, rich protocol data outside of the one provided by our standard set of Unmarshal APIs.

How do I access it?

Refer to

Markdown 7094 bytes 778 words 114 lines Ln 110, Col 86HTML 3521 characters 755 words 44 paragraphs
4:28
# How do I access my Smart Contract data Through Metabase?


![](https://lh3.googleusercontent.com/132faBxMUhuJMT72aTZm8xgBmcETUuHtZwlI98INy6amlyY930kFabXKmQ8AWzpY8ogyV5u3sz2yUtDfqB_hV5izgoFAN8vAe1cQuV92NNXlJhIG9ql6FTLTjTkjLj8CLKGcn5X0oL0WOvPrjNrrz0U)


Now that you are done with creating your parser, which is actively tracking your data, parsing it, and saving it to a Postgres database, let's move to the question of how to access the data?

For data access, we provide add-ons to our users. One of these add-ons is Metabase.

Metabase is an open-source tool to help you extract information from your data. You can use Metabase to build out beautiful internal and public dashboards, save and share queries, etc.

Before getting started with Metabase, let's revisit the structure of your indexed data.

## Understanding the structure of your data

In the Parser series (Part 2): Creating your first parser?, we deployed a parser for the Marsh ERC20 contract, we will continue to use it as an example.

-   When you create your parser you are asked to enter the database name in which your data is to be indexed. The database name corresponds to a schema in Postgres.


![](https://lh4.googleusercontent.com/ex9tPLseFu0b6AOyWfiaRF7_GFWsiw1tU09hOGh_5bY77jr7LQyshk4EInFT7TIjb6uTwk3IriTCDKXmAdzXJmrPNQ5XPXYq9WkyHBeap97WnZ1J6yNosdlMkw20SM9w8ypdHxU3BXhJeoeMClN3lsk)

*Fig. 1.1 Parser form highlighting the database name field*

-   Don't remember the name you gave? The name of the schema where your parser is writing data can be found under the View details section.


![](https://lh5.googleusercontent.com/jB05Q9qpNlXAxksywrretSRCUrSuBMIgMrmSMLGqbTwZdO-eIJ793Fv_krqP4piOr07xR52cBkLjBJ1LnDfCN-nu7bQEd_ncEFrIyqm-n36NfdKLv3pAMu81qen1ng-KzsYE4J8d27Ndpaxymev-ktA)

*Fig 1.2 Parser listing screen view details section*

![](https://lh4.googleusercontent.com/MpVHNaXYCL75EwiZNbIUGsQeUCdG_x9sriKhU9TbqugLhVgWC3R5eUhZ53Yv1uDuSxVFx1UZiY70G7reoDwgfvk9670WT8bHjBpvIGYyTWqW4loHtSVHC6fW_Oe22rJHjlYjDsvj_PBpBhFkDk6WzmY)

*Fig 1.3 Schema name in the parser View details window*

-   As initially mentioned, all of your data tables are saved under this schema.

-   The data of each of the contract events/functions selected for indexing(at the time of parser creation) is saved into corresponding tables.


**Table nomenclature**

-   All of the table names are in snake case and are postfixed with _events and _methods for event and function tables respectively.


In the above example, we selected the following events and functions for indexing

1.  Events: Approval, Transfer

2.  Functions: transferFrom


We could expect to see find the following tables in our schema

1.  Event tables: approval_events, transfer_events

2.  Function tables: transfer_from_methods


## Logging in to Metabase

**TL;DR**

You can find your Metabase credentials under the parser section on the Unmarshal console page. It is important to note that you will only be able to view your Metabase credentials once you have deployed at least one parser.

**Detailed steps**

-   Click on the View details in the Metabase Add-On


![](https://lh3.googleusercontent.com/JTo_0ekFFnqvMPMqR0kTkIRtOZXyK-x9OqH3tG7774-7O3zkXuSHIhKPbz2y8boBb12yppIwaxGAseVsu0DVJYuctBfm8dkT1Q5i-pKdFPmZmvmUDVa1XMRfcalryhx1y1yQmzZ5J6BzhjE_mYUOzQQ)

*Fig. 1.4 Metabase add-on view details section*

-   Click on the URL available in the Metabase popup window


![](https://lh5.googleusercontent.com/keFwiPsNCE0tUKzgZahRTnhmIkQ9zQwsk6k3u6asWb__jG-lehEApiesy-DjT32Zu7irp26jUT1Y6AE4yxkYJ78uJlhGnODcHG_kM3TNA01b9Flwtljb4uCnjTv7RNAeyxcOs_dq2No6Ftt_WNxopgQ)

*Fig. 1.5 URL in Metabase View details window*

-   Use the above credentials to log into Metabase

-   And just like that, you are one step closer to curating information from the data collected by your parser


## Getting used to Metabase

> "Great, I can see the Metabase homepage but what does it all mean?" Might be the immediate next question you have if you are not already familiar with Metabase.

In this section, we would be going over the terminology commonly used when working with Metabase. If you are already familiar with Metabase feel free to skip this section.

Metabase is a widely used tool, and has a lot of learning resources online, to help in your analytics.

## **Terminology**

![](https://lh5.googleusercontent.com/hmsj033Q0EgtbMVEtxKd9Lv75vnAKX6N_Z6XnUcl7_OUiBNJ7sIKuDs0B3WBwFB1PBVzXzK2Rr5QgmiedJ2i6KAKNIFU6lNixJCR5-GAUWBd85OFcyJ2t--4nEY0RwiCreGUJSif-wzfMzA6aCwZPqY)

*Fig. 1.6 Metabase homepage highlighting sections*

**Data (1)**

![](https://lh4.googleusercontent.com/gRhUVgI7L1YGbIMMcw4bxQbYwxPf6_O3G9HfFDKr-ZTzPC2CNqF7nZpr4zovBf5S0MweAtQKoxnNSu5zPeZMt_9cc1oVobvCZNhkBmCq1uLgdkLToFJIhHr9wONojS3CrlkjWepk_j55afXzgP7aIG4)

*Fig. 1.7 Browse data screen within Metabase*

1.  This section serves as a GUI client for the data collected for your indexers.

2.  On clicking browse data, you get a data source with your Unmarshal console username. (Fig. 1.7)

3.  Digging a little deeper into the data source with your username, you see one of two.

4.  The tables in the data source if, you only have a single schema in which a parser is deployed. Metabase defaults the view to the only available schema.

5.  A list of available schemas across which your parsers have indexed the data. (Fig 1.8)

6.  In our case, we have deployed multiple parsers from our account in different schemas and hence we see a list of schemas.

7.  Within each of the schemas, you have your data tables as described before. (Fig 1.9)

8.  Here is the table structure within our marsh_erc20_parser schema.

9.  This section in Metabase helps you give a nice overview of the data you are working with.


![](https://lh6.googleusercontent.com/tmQoV9taep_2ohsOwqs4aa-C7b_V8wucBox2uUYoFc1sQxZ05O4QjLbqzxD6zashjpRl7QylOAKI4SnrOUb71HGJwU2ASqkEsiDTDL-tIslqyVzFsRqscUUVEvVTEFPrVH2CSQttG6hEX1L9VMHzdcE)

*Fig 1.8 Schemas available in your data source*

![](https://lh3.googleusercontent.com/dy5NXxsbrZZTp28248sppUyKpFGSaZJAY7fWtez8td4s_-j-jJnEVsMjKD-fzohHziywG5HJHYQs8GiqoWyVwtFU4CW-2YuqGPgc5SdUr0HtvyMN-Gba815g0wjVRdpmWexyskVf0OdEE05cbeQd2g8)

*Fig 1.9 Table structure within the marsh_erc20_parser schema*

**Questions and SQL (2)**

1.  More often than not, you would want to curate specific information from the data tables.

2.  To do this you could either choose to write a custom SQL query or you could use the query builder abstraction which Metabase provides also known as Question.

3.  SQL is a powerful yet relatively simple data access abstraction to work with. If you are unfamiliar with it there is tons of documentation and guides available to help you out. (As we save your data in a Postgres database, be sure to refer to related documentation)

4.  Given that you have become familiar with SQL, writing your first query might still need some help given the hierarchy of schemas and data tables, we will get to this in a moment.

5.  Metabase also lets you visualise the results of Questions/SQL queries in different forms like pie charts, tables, line graphs, bar graphs, etc.


**Card (3)**

1.  A card symbolises a saved question or SQL query along with its visualisation settings.


**Dashboard (4)**

1.  A dashboard is a single page within which multiple cards can be embedded into.

2.  The cards can be resized and moved around to increase the readability of your curated cards.

3.  Apart from having login limited access to the dashboard, the dashboard could also be made public.


**Collection (5)**

1.  This is a grouping feature in Metabase that lets the users aggregate data based on logical affinity.

2.  By default, you have access to Our analytics, a collection where all of the public dashboards reside and Your personal collection where all sub-collections which only you have access to reside.

3.  As hinted at in the previous point, you can have nested collections in Metabase, which lets you better group your information.


## Querying your data through SQL

Metabase makes it easy for you to curate data using the Question query builder. But un-avoidably there would be cases where you have to write your SQL queries.

This is not intended on being a guide on writing PostgreSQL queries, there is an abundance of that available online. Here, using an example we want to highlight the schema and table relationship to help you along the way.

Let's suppose you are looking for an answer to the following question,

Question: Get me the total number of transfers made on the marsh smart contract along with the volume in $MARSH between 2022–02–07 and 2022–02–08

![](https://lh6.googleusercontent.com/etn103eaOSkXdGVHJveNvJr9tRmkNmpIO0kJHREmok2PaFl-tGz_PgAElcs49LkLFvTC6XVD2NgiOwQYVOOUMLVRZGX6ybodrCo96j9AOi1DghqLRBKgLeRLhHbtcw-t9WmplW0xo9zbiMWxpszaQ04)

*Fig. 1.10 SQL query editor on Metabase*

**Query**

```
SELECT
	count(id), transfer_count,
	sum(value::numeric)/1e18 transfer_volume
FROM marsh_erc20_parser.transfer_events
WHERE block_time
BETWEEN timestamp '2022–02–07'
AND timestamp '2022–02–08';
```
Here is what the query would look like.  **It is important to note the hierarchy of the data.**  Since the data for the transfer event is saved within the schema in which the parser is deployed, to access the data a similar hierarchy will have to be used.

## **Challenge**

Here is a challenge for you. For your parser complete the following and tag us on Twitter with  **#UnmarshalParser**, we would pick the best dashboards and make them public to showcase them on  [Unmarshal Analytics Showcase](https://analytics.unmarshal.io/)

1.  Create a collection in your personal collection
2.  Create your first query
3.  Save your query as a Card
4.  Create a dashboard
5.  Play around and make it as informative as possible

## Advanced level

> By now you should be fairly familiar with Metabase and the structure of your data!

In this section, we would go over a couple of powerful tools that you would feel the need for when building complex dashboards.

**Cross schema querying**

Sooner than later, you will have requirements where you have to aggregate data from multiple smart contracts e.g. if you have multiple smart contracts powering your DAPP.

As mentioned previously, we index your data in Postgres schemas, and Postgres supports cross-querying across all of your schemas making this a non-issue.

**Making dashboards public**

Reach out to Unmarshal either on [Telegram](https://t.me/Unmarshal_Chat), [Twitter](https://twitter.com/unmarshal) or Discord and we can help you out with this. Once your dashboard has been made public by the Unmarshal team, you will get a link which can either be directly used or embedded in your web application using an IFrame.
