## Omnibar search in your website

#### What is omnibar search ? 
In Google Chrome, the Omnibox feature combines a browser’s address bar and search box into one single area at the top of the browser window. You can also use it to bookmark websites and see security information about your current webpage.

Just type your query into the address bar and press Enter. But what you may not have known is that you can also search for a word or phrase on a specific website. To search on a specific website, just enter website homepage url and followed by a space with search string in omnibar. 
eg. google.com[blank_space]searchterm. 

[![Eg Omnibar search ](https://i.ibb.co/BBcbdKP/omnibar.png "Eg Omnibar search ")](https://i.ibb.co/BBcbdKP/omnibar.png "Eg Omnibar search ")

#### Implementing omnibox support with search suggestions

Follow below steps to implement omnibar search in your website. 
- Save the following code as search.xml


    <OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/" xmlns:moz="http://www.mozilla.org/2006/browser/search/">
      <script></script>
      <ShortName>Site Name</ShortName>
      <Description>Site Description (eg: Search sitename)</Description>
      <InputEncoding>UTF-8</InputEncoding>
      <Image width="16" height="16" type="image/x-icon">Favicon url</Image>
      <Url type="application/x-suggestions+json" method="GET" template="http://suggestqueries.google.com/complete/search?output=firefox&q={searchTerms}" ></Url>
      <Url type="text/html" method="GET" template="http://yoursite.com/?s={searchTerms}" ></Url>
      <SearchForm>http://yoursite.com/</SearchForm>
    </OpenSearchDescription>

 - Upload search.xml to the root of your site
 - Add the following meta tag to your site's <head> tag
  `<link rel="search" href="http://www.yoursite.com/search.xml" type="application/opensearchdescription+xml" title="You site name"/>`
 
- Make sure to replace the domain urls with your domain.
