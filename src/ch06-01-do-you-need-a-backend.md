# Use the right kind of database

Don't default to creating a backend server or a database if you don't need to. There may be alternatives, such as a JAMStack, static JSON file or just plan old HTML, which in combination with cloud-based online services could provide the functionality you need without the many overheads (environmental and otherwise) of running your own servers.

## The Problem

All too often, developers will reach straight for popular stacks or familiar stacks for everything. Stacks such as;

- **LAMP/MAMP** (Linux/Mac, Apache, MySQL, PHP) - arguably the stack that popularized "stacks" in web development.
- **LYME** (Linux, Yaws, Mnesia, Erlang)
- **MEAN/MERN/MEVN** (Mongo, Express, Angular/React/Vue, Node)

These stacks are popular conventions and there will of course be times when these are the perfect solution - a LAMP based solution, for example, provides a simple deployment model that can easily be performed by people with very little technical experience. This gives everyone the ability to deploy "out of the box" solutions to common problems.

Oftentimes though, these stacks are **used by default without considering alternatives**. LAMP-stack based library Wordpress, for example, reportedly powers [42% of the web](https://wordpress.com/) and has a huge and vibrant ecosystem. There's no disputing that Wordpress is an excellent CMS, but how many of those sites are just a couple of static pages and a contact form?

## The Alternative

Consider the aforementioned scenario, where a customer simply wants some static content and some kind of form, maybe one that sends emails. You can achieve this using static HTML and some online services;

- If the customer will never be editing the content themselves, why plug in a CMS? You could either just hard code the static content, write it in [Markdown](https://en.wikipedia.org/wiki/Markdown) files or even put it into a local [JSON](https://en.wikipedia.org/wiki/JSON) file.
- If the customer wants the ability to edit content themselves, consider providing this feature through a cloud based content platform such as [Sanity.io](https://www.sanity.io/).
- If the customer wants a contact form, the hosting provider [Netlify](https://www.netlify.com/) provides hosting for static sites, plus the abiltiy to [create custom forms](https://docs.netlify.com/forms/setup/) to collect feedback. Alternatively you could use an email platform such as [SendGrid](https://sendgrid.com/).

The tooling around JavaScript is so good these days that implementing the above might not be as tricky as you would think. On top of this, most online services will be run out of the "big three" cloud providers (Microsoft, Google and Amazon) who all have made sustainability pledges and are comitted to moving towards 100% renewable energy. Cloud based solutions often also implement sustainable scaling strategies to ensure their resources are being used efficiently.

It'll probably cost quite a lot less than running a server 24/7 too.

## JAMstack

JAMStack (Javascript, APIs and Markup) is a modern approach to creating web applications where you handle the layout, functionality and content on the client using JavaScript and Markdown. Any functionality that cannot be handled on the client (such as sending emails) is handled using APIs, be they either online services or APIs you write yourself.

The advantage of all this is that you don't have a server running around the clock waiting for requests that may never come. Popular JAMStack frameworks include [Next.JS](https://nextjs.org/), [Gatsby](https://www.gatsbyjs.com/) and [Hugo](https://gohugo.io/).

## Databases

On the database front, oftentimes people will spin up a database server purely because they believe that is the only option for storing data... but you might be able to get away with a simple JSON file containing the whole database. This could then be cached locally (depending how big it is) and hey presto - all data access is happening locally and no data is being sent over the wire.

If you are working mainly with static data

- That changes infrequently
- That is only really edited by power users or developers
- With simple access patters such as "get by id" or "filter by category"

Then **you probably don't need a database** - another carbon (and money) expense you can get rid of, plus another boost to your application's performance. Choosing JSON as a format also means you have an easier path to migrate to a database should you ever decide you need one, as JSON is the format used by popular solutions such as [MongoDB](https://www.mongodb.com/) and [CouchDB](https://couchdb.apache.org/).

It's also **one less security concern** for you to worry about, as online providers will often take care of data protection concerns such as backups and data integrity for you.

## Relevant Links

- [JAMStack.org](https://jamstack.org/) - A comprohensive guide for building JAMStack sites.
- [StackShare.io](https://stackshare.io/) - see what stacks other companies are using.
