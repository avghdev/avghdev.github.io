---
layout: article
title:  "Jekyll - An Analysis"
date:   2018-02-15
categories: development
image:
    teaser: jekyllf.png
    feature: jekyll_feature.png
comments: true
---

I promised to make a in-depth post on Jekyll, so here is a post containing more than you will likely ever need to know. I've included a table of contents so you can skip past the bits you don't need/want.

### What is Jekyll?

Put simply, Jekyll is a "static website generator". For those of you who don't have a background in web development, a static website *generator* makes *static websites*. Of course that is obvious from the name - but it might be helpful to know the difference between a **static** and a **dynamic** website.

##### <u>Static website</u>

A **static** website is a site that is programmed using only HTML (Hyper Text Markup Language) and CSS (Cascading Style Sheets). Static websites have several advantages:

- **Fast:** Because static websites are written solely in Markup Language, they inherently do not generate any material from a database. This cuts out the "middle-man" between the server and the client. This is why static websites will almost always run faster than dynamic websites under equivalent circumstances.

- **Flexible:** Since static websites do not generate any content from a database, it is easy for the developer to make greatly varied webpages.

- **Easy Up-Front Development:** It is usually faster, easier, and therefore cheaper to develop static websites up-front than dynamic websites. This is largely attributed to the fact that static websites do not typically have scripting languages to worry about (e.g. PHP, JavaScript, ASP), nor databases to integrate.

<div class="notice-warning">
<b><u><h5 style="margin: 0px; margin-bottom: 6px; text-decoration: underline">Note</h5></u></b>
<p style="margin: 0px">Static websites <i>can</i> be written with JavaScript, since it is a client-side language. But, JavaScript cannot interact with any server-side languages for the site to still be considered static.</p>
</div>

However, due to the limited nature of static websites, they have a significant amount of disadvantages as well. These often turn people away from developing static websites in professional settings. Some of these disadvantages include:

- **Tedious to Update:** Unlike dynamic webpages, static webpages do not pull from a database to make their content. This means that a developer has to update each page on the website whenever a new functionality, feature, or theme is added. This makes website overhauls an especially tedious undertaking.

- **Scalability:** Due to the same reasons as above, making a large website - such as for an e-commerce company - can be a huge task. The developer might have to make individual pages for each product, for example, even if each page shares similar features.

- **Costly Ongoing Development:** More time and effort equals a higher cost. We can see from above that any updates to a static website will likely take a considerable amount of both.

##### <u>Dynamic website</u>

A **dynamic** website, as the name implies, generates content *dynamically*. It achieves this by accessing content from a database or CMS through scripting languages like PHP. This functionality gives dynamic sites a leg-up over static ones in a few ways:

- **Content Management:** In the "real world", clients of web developers often *never* want to see, touch, or really have anything to do with the underbelly of the website. That's where Content Management Systems (or CMS') come in. CMS' allow clients to update their website from a nifty graphical dashboard. You see this approach being used in the supremely popular [WordPress](https://wordpress.com/) Admin Dashboard. Some developers also use different forms of CMS' to *manage* their content - and will even create a custom CMS for either themselves or their client. Of course, for all this to work the website needs to be dynamic (i.e. it must be able to access and generate content from a database).

  <figure>
      <img src="{{site.baseurl}}/images/jekyllimg.png " />
      <figcaption>Example of the CMS WordPress dashboard.</figcaption>
  </figure>

- **Site-Wide Updates:** Since most/all of a dynamic websites content is generated from a database, site-wide updates are generally easy to achieve. You simply make a change to some template that the database is generating content from and voila, the change has been implemented across every page that uses that template.

- **Minimal On-Going Costs:** The functionality described above makes updates after the initial creation of the site easy to handle. This means less time *and less money* spent on development.

As you can see, dynamic websites improve on many of the key detriments of static websites. This is why most developers believe that dynamic websites are the best choice -  except in rare situations. But dynamic websites are not without their faults:

- **Less Flexible Design:** The same template-like functionality that makes dynamic websites easy to update make them stiff in terms of design. Unlike static websites, we know that dynamic websites will pull from a database to generate content on each page. This means that the overall design of each page will be more or less limited to the templates your database pulls from. This can lead to "sameness" across your website.

- **Harder Up-Front Development:** Up-front development for dynamic websites can be a much bigger, longer, and more expensive ordeal. This is due to a dynamic websites intimate relationship with servers, databases, and all the scripting that goes a long with it. For many, the cost of the up-front development is made up for in the end. However, for smaller and simpler websites, a static choice might be a better option due to this weakness.

- **Complexity:** The nature of dynamic websites makes them much more complex beasts than static websites. With dynamic websites a developer usually has to deal with at least three different languages - the HTML for the website, the server-side scripting language (e.g. PHP, ASP, etc.), and the data query language (e.g. SQL). That can be a lot to deal with - especially for a single developer. It's also worth mentioning that dynamic websites that make use of a CMS have a whole other level of complexity associated with them.

- **Security:** Particularly when making use of a CMS, dynamic websites can run into a lot of security issues. This is due to the fact that  they often store sensitive data in an online database, and that many of the most popular CMS's are targets for hackrerw. WordPress, for example, is infamous for being a vulnerable system. They frequently release security updates to try and maintain security, but updating so often can be tedious. Matt Billman illustrates this issue in [his awesome article](https://www.smashingmagazine.com/2015/11/modern-static-website-generators-next-big-thing/) for *Smashing Magazine*, writing "we pay a huge price for the underlying complexity of dynamic code running on a server for every request".

<figure>
    <img style = "max-height: 400px" src="{{site.baseurl}}/images/dynvsstat.png " />
    <figcaption>An illustration depicting the static process vs the dynamic process (courtesy <a href="https://about.gitlab.com/2016/06/03/ssg-overview-gitlab-pages-part-1-dynamic-x-static/">gitlab</a>)</figcaption>
</figure>

<div class="notice-info">
  <b><u><h5 style="margin: 0px; margin-bottom: 6px; text-decoration: underline">Additional Resources</h5></u></b>
  <p style="margin: 0px"><i>Some resources for additional learning on this subject</i></p>
  <p style="margin: 0px">
    <a href="http://www.spiderwriting.co.uk/static-dynamic.php" >Spider Writing</a> |
    <a href="https://about.gitlab.com/2016/06/03/ssg-overview-gitlab-pages-part-1-dynamic-x-static/">GitLab</a> |
    <a href="https://www.javatpoint.com/website-static-vs-dynamic">javatpoint.com</a> |
    <a href="https://www.pluralsight.com/blog/creative-professional/static-dynamic-websites-theres-difference">Plural Sight</a>
  </p>
</div>

Hopefully with that knowledge it will become clear what exactly a "static website generator" is.

#### What's the point of static website generators?

It's good to know what a static website generator is, but it is more important to know *why* you would want to use one in the first place. It turns out that by using a static generator, you get many of the benefits of dynamic websites with all the functionality of static websites. For example, because many static site generators - including Jekyll - generate the website based on a template directory (more on that later), you can design your website so that it updates very easily. Additionally, because the website is always converted into a static site, it will load at the same awesome speeds as a "vanilla" static site would. We will delve more into the benefits later, but for now it should suffice to know that **static site generators attempt to find a middle ground between dynamic and static solutions**.
